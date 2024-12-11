---
layout: post
title: Get all users that have access to Citrix
Date: 2024-11-11
categories: [ Powershell, Citrix, CVAD]
thumbnail: "assets/images/database_upgrade.png"
description: Understanding user access within a Citrix environment is crucial for security and management purposes. To facilitate this, I've developed a script to identify and report on user access privileges.
---

### How to use

This script automates the process of identifying and mapping published applications to their associated users. It leverages Citrix PowerShell SDK and Microsoft Active Directory PowerShell module to retrieve and analyze application and group membership information.

Key Features:

- Comprehensive Application and User Mapping: Scans all published applications and determines their corresponding group memberships.
- Detailed Reporting: Generates a detailed report listing users and their assigned applications.
- Error Logging: Logs failed checks related to user groups and individual users.


Configurable Options:

- adminaddress = Specifies the address of the Delivery Controller. (FQDN)
- userlist = Defines the location and filename for the user-application mapping report.
- failedgrouplist = Specifies the location and filename for the failed group check report.
- faileduser = Defines the location and filename for the failed user check report.
- maxrecods = Sets a limit on the number of applications to be checked.
- domainnamelenght = Specifies the length of the domain name, including the domain separator ('/'), to accurately identify users and groups in the Citrix environment.


{% raw %}
```powershell
$Startdate = (Get-Date)

#set all parameters for the code
$adminaddress = "(Delivery Controller)"
$userlist = "(Location of the file)\Citrix_users.csv"
$failedgrouplist = "(Location of the file)\Citrix_Failed_usergroups.csv"
$faileduser = "(Location of the file)\Citrix_Failed_user.csv"
$maxrecods = 100000000
$domainnamelenght = 3

#Set the parameters for the progressbar
$progressParams = @{
    Activity = "Processing data"
    status = "In progress"
    PercentComplete = 0
    CurrentOperation = "Initializing"
}
#Show the start in the progressbar
Write-Progress @progressParams

$data = $null
$count = 1

try{
#Request all the applications from Citrix
$applications = Get-BrokerApplication -adminaddress $adminaddress -MaxRecordCount $maxrecods
    }
catch{
Write-host "Failed to contact Delivery Controller $adminaddress" -ForegroundColor red
exit
    }

#Count the number off applications and add 1 extra
$applicationscount = $applications.count + 1

#Start the check foreach application
foreach($application in $applications){

    #Start with one member at the time
    foreach($members in $application.AssociatedUserNames){ 

        foreach($member in $members){

            #Reset the fail check values
            $Userdata= $Null
            $continue = $False
            $usererror = $False
            $usererrorfilter = $False
            $faileduser = $False
            $failedgroup = $False

            try{
                #Check if it's a user and remove the domain from the user
                Get-ADUser $member.substring($domainnamelenght) -ErrorAction stop | Out-Null
                $username = $member.substring($domainnamelenght)
                
                Try{ 
                    #Get User data Country, Company and Department
                    $Userdata = get-aduser $username -Properties Country, Company, Department | select Country, Company, Department
                    $continue = $True
                    }
                Catch{
                    #Register if the check fails
                    $usererror= $True
                    }

                #Check if the previous check fails  
                if($usererror){
                    Try{ 
                        #Get User data Country, Company and Department based on the name of user instead of samaccountname 
                        $Userdata = get-aduser -filter 'Name -like $($username)' -Properties Country, Company, Department | select Country, Company, Department
                        $continue = $True
                        }
                    Catch{
                        #Register if the check fails
                        $username | Out-File $faileduser -Append
                        }
                    }
                
                if($continue){
                    #Put the data of the user in a Array                                  
                    $data += @([pscustomobject]@{
                                Username=$username;
                                Applicationname=$application.ApplicationName;
                                Applicationfolder=$application.ClientFolder;
                                Country=$Userdata.country;
                                Company=$Userdata.Company;
                                Department=$Userdata.Department;
                                })
                    }
                }
            catch{
                #If the application member is not a user it will fail and set parameter to do a group check
                $faileduser = $True
                }
            
            #If the application member is a group it continue over here 
            if($faileduser){
                try{
                    #Get all the group members and remove the domain from the member
                    $groupmember = Get-ADGroupMember $member.substring($domainnamelenght) -Recursive
                    $groupmembers = $groupmember.name 

                    #check each user
                    foreach($username in $groupmembers){
                        
                        #Reset the fail check values
                        $usererror= $False
                        $usererrorfilter= $False
                        $Machine = $False
                        $computer = $Null
                        $continue = $False
                        $Userdata = $Null

                        Try{
                            #Get User data Country, Company and Department based on samaccountname 
                            $Userdata = get-aduser $username -Properties Country, Company, Department | select Country, Company, Department
                            $continue = $True
                            }
                        Catch{
                            #Register if the check fails
                            $usererror= $True
                            }

                        #Check if the previous check fails  
                        if($usererror){
                            Try{ 
                                #Get User data Country, Company and Department based on the name of user instead of samaccountname 
                                $Userdata = get-aduser -filter 'Name -like $($username)' -Properties Country, Company, Department | select Country, Company, Department
                                $continue = $True
                                }
                            Catch{
                                #Register if the check fails
                                $usererrorfilter= $True
                                }
                            }
                        #Check if the previous check fails  
                        if($usererrorfilter){
                            Try{
                                #Check if the user is a computer
                                $computer = get-ADComputer $username
                                $Machine = $True
                                $continue = $True
                                }
                            Catch{
                                #Register if the check fails
                                $username | Out-File $faileduser -Append
                                }
                            }
                        if($continue){
                            #Put the data of the user in a Array 
                            $data += @([pscustomobject]@{
                                                        Username=$username;
                                                        Applicationname=$application.ApplicationName;
                                                        Applicationfolder=$application.ClientFolder;
                                                        Country=$Userdata.country;
                                                        Company=$Userdata.Company;
                                                        Department=$Userdata.Department;
                                                        Group=$member.substring($domainnamelenght);
                                                        })
                            }
                    }
                }

                catch{
                    #If the application group is over 5000 user it will fail and register this
                    $failedgroup = $True
                    }
                }

            #Check the Group on another way if it's failed because it's over 5000 users
            if($failedgroup){
                try{
                    #Get all the group members and remove the domain from the member
                    $groupmember = Get-ADGroup $member.substring($domainnamelenght) -Properties Member | Select-Object -ExpandProperty Member | Get-ADObject | select name | sort name
                    $groupmembers = $groupmember.name

                    #check each user
                    foreach($username in $groupmembers){

                        #Reset the fail check values
                        $usererror= $False
                        $usererrorfilter= $False
                        $Machine = $False
                        $computer = $Null
                        $continue = $False
                        $Userdata = $Null

                        Try{
                            #Get User data Country, Company and Department based on samaccountname 
                            $Userdata = get-aduser $username -Properties Country, Company, Department | select Country, Company, Department
                            $continue = $True
                            }
                        Catch{
                            #Register if the check fails
                            $usererror= $True
                            }

                        #Check if the previous check fails
                        if($usererror){
                            Try{
                                #Get User data Country, Company and Department based on the name of user instead of samaccountname
                                $Userdata = get-aduser -filter 'Name -like $($username)' -Properties Country, Company, Department | select Country, Company, Department
                                $continue = $True
                                }

                            Catch{
                                #Register if the check fails 
                                $usererrorfilter= $True
                                }
                            }
                            
                        #Check if the previous check fails   
                        if($usererrorfilter){
                            Try{
                                #Check if the user is a computer
                                $computer = get-ADComputer $username
                                $Machine = $True
                                $continue = $True
                                }
                            Catch{
                                #Register if the check fails
                                $username | Out-File $faileduser -Append
                                }                                         
                            }

                        if($continue){
                            #Put the data of the user in a Array 
                            $data += @([pscustomobject]@{
                                                        Username=$username;
                                                        Applicationname=$application.ApplicationName;
                                                        Applicationfolder=$application.ClientFolder;
                                                        Country=$Userdata.country;
                                                        Company=$Userdata.Company;
                                                        Department=$Userdata.Department;
                                                        Group=$member.substring($domainnamelenght);
                                                                        })
                                }
                        }
                    }

                catch{
                    #Register if the group cannot be checked
                    $member.substring($domainnamelenght) | Out-File $failedgrouplist -Append
                    }
                }

            }

        }
    #update the status bar
    $progressParams.PercentComplete = ($count / $applicationscount) * 100
    $progressParams.CurrentOperation = "Processing item $count of $($applicationscount)"
    Write-Progress @progressParams
        
    $count++
    
    }

#update the status bar
$progressParams.PercentComplete = ($count / $applicationscount) * 100
$progressParams.CurrentOperation = "Merging Licenseserver users with list"
Write-Progress @progressParams

#Export the data to csv
$data | Export-Csv -path $userlist -NoTypeInformation

#Calculate duration time
$enddate = (Get-Date)
$duration = New-TimeSpan -start $Startdate -End $enddate
Write-Host "The run was $($duration.hours):$($duration.minutes)" -ForegroundColor Green

#Finish the status bar
Write-Progress -Completed -Activity "Completed"
```
{% endraw %}