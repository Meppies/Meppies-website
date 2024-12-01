---
layout: post
title: Visual Studio Code Extensions
Date: 2024-01-05
categories: ["Visual Studio Code", Extension]
thumbnail: "assets/images/Extensions.png"
description: Visual Studio Code is a powerful tool that can be enhanced with a variety of extensions to make coding more efficient and enjoyable. Here are some popular extensions that can help you with code checking, code prediction, and visualization.
---

# Why extensions

Visual Studio Code is a powerful tool that can be enhanced with a variety of extensions to make coding more efficient and enjoyable. Here are some popular extensions that can help you with code checking, code prediction, and visualization.

## Ansible 
The Ansible VS Code Extension by Red Hat is a Visual Studio Code extension that adds language support for Ansible to Visual Studio Code. The extension provides syntax highlighting for Ansible keywords, module names and module options, as well as standard YAML elements. It also supports Jinja expressions, which are used in Ansible conditionals (when, failed_when, changed_when, check_mode), and provides suggestions for smart autocompletion. The extension verifies the syntax of your Ansible scripts while you type and provides feedback instantaneously. It also integrates with ansible-lint, which is executed in the background on opening and saving a document, and any findings are presented as errors. You can activate the extension manually by opening a folder containing Ansible files with a VS Code workspace

[Ansible](https://marketplace.visualstudio.com/items?itemName=redhat.ansible)
<br>
<img src="https://redhat.gallerycdn.vsassets.io/extensions/redhat/ansible/2.9.118/1700737333114/Microsoft.VisualStudio.Services.Icons.Default" alt="Ansible" width="50"/>



## Bracket Pair Colorization Toggler 
The Bracket Pair Colorization Toggler is a Visual Studio Code extension that provides a simple command to quickly toggle the global “Bracket Pair Colorization” setting. This extension is useful for developers who work with code that contains many nested brackets. The extension allows you to quickly turn on or off the colorization of matching brackets, making it easier to read and understand your code

[Bracket Pair Colorization Toggler](https://marketplace.visualstudio.com/items?itemName=dzhavat.bracket-pair-toggler" target="_blank)
<br>
<img src="https://dzhavat.gallerycdn.vsassets.io/extensions/dzhavat/bracket-pair-toggler/0.0.3/1675812133561/Microsoft.VisualStudio.Services.Icons.Default" alt="Bracket Pair Colorization Toggler" width="50" />


## Code Spell Checker 
The Code Spell Checker is a Visual Studio Code extension that provides a basic spell checker for code and documents. It helps catch common spelling errors while keeping the number of false positives low. The extension works by highlighting words that are not in the dictionary files with a squiggly underline. It also provides suggestions for correct alternatives.

[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)
<br>
<img src="https://streetsidesoftware.gallerycdn.vsassets.io/extensions/streetsidesoftware/code-spell-checker/3.0.1/1694424431035/Microsoft.VisualStudio.Services.Icons.Default" alt="Code Spell Checker " width="50" />

## Draw.io Integration
The Draw.io Integration is a Visual Studio Code extension that allows you to create and edit diagrams using the Draw.io editor without leaving your code editor. The extension supports editing of .drawio, .dio, .drawio.svg, and .drawio.png files. You can create a new diagram by creating an empty file with one of these extensions and opening it. The extension provides a command to convert between different formats. It also supports multiple Draw.io themes and allows you to use Liveshare to collaboratively edit a diagram with others.

[Draw.io Integration](https://marketplace.visualstudio.com/items?itemName=hediet.vscode-drawio)
<br>
<img src="https://hediet.gallerycdn.vsassets.io/extensions/hediet/vscode-drawio/1.6.6/1674119919721/Microsoft.VisualStudio.Services.Icons.Default" alt="Draw.io Integration" width="50"/>

## Git History
The Git History is a Visual Studio Code extension that provides a comprehensive view of the Git commit history of a file or folder. It allows you to view the details of a commit, such as author name, email, date, and comments, and view a previous copy of the file or compare it against the local workspace version or a previous version. The extension also supports viewing the changes to the active line in the editor (Git Blame), configuring the information displayed in the list, and using keyboard shortcuts to view the history of a file or line 

[Git History](https://marketplace.visualstudio.com/items?itemName=donjayamanne.githistory)
<br>
<img src="https://donjayamanne.gallerycdn.vsassets.io/extensions/donjayamanne/githistory/0.6.20/1678008598739/Microsoft.VisualStudio.Services.Icons.Default" alt="Git History" width="50"/>

## GitHub Copilot
GitHub Copilot is an AI pair programmer tool that helps you write code faster and smarter. You can use the Copilot extension in Visual Studio Code to generate code, learn from the code it generates, and even configure your editor. It provides suggestions for numerous languages and a wide variety of frameworks, and it works especially well for Python, JavaScript, TypeScript, Ruby, Go, C# and C++. Copilot presents suggestions automatically to help you code more efficiently. There are just 3 steps to harnessing these suggestions:

1. Start writing code (or code-related items, like comments or tests).
2. Copilot provides suggestions for a variety of languages and frameworks. For any given input, Copilot may offer multiple suggestions. You can select which suggestion to use or reject all suggestions.
3. Receive a Copilot suggestion in gray ghost (faded) text. Ghost text is placeholder text that will be replaced by input you type or select from Copilot 

[GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
<br>
<img src="https://github.gallerycdn.vsassets.io/extensions/github/copilot/1.143.601/1702570386943/Microsoft.VisualStudio.Services.Icons.Default" alt="GitHub Copilot" width="50"/>

## GitLens
GitLens is a free open-source extension for Visual Studio Code that provides a rich set of features to help you better understand, write, and review code. GitLens supercharges your Git experience in VS Code by providing valuable insights into code authorship and unlocking the full power of Git. Some of the features of GitLens include:

* **Code Lens**: Displays information about who last modified a line of code, when it was modified, and whether there are any conflicts.
* **Blame Annotations**: Shows the Git blame information for the current line of code.
* **Commit Search**: Allows you to search for commits by author, message, or file.
* **File History**: Shows the history of a file, including all changes made to it.
* **Code Navigation**: Allows you to easily navigate through code by jumping to definitions, references, and symbols

[GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
<br>
<img src="https://eamodio.gallerycdn.vsassets.io/extensions/eamodio/gitlens/2023.12.2004/1703063273544/Microsoft.VisualStudio.Services.Icons.Default" alt="[GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
" width="50"/>

## HashiCorp Terraform
HashiCorp Terraform is an open-source infrastructure as code software tool that enables you to define and provision a data center infrastructure using a high-level configuration language. The Terraform Extension for Visual Studio Code provides editing features for Terraform files such as syntax highlighting, IntelliSense, code navigation, code formatting, module explorer, and much more. Some of the features of the Terraform Extension include:

* Syntax Highlighting: Highlights syntax from Terraform 0.12 to 1.X.
* IntelliSense: Provides auto-completion of providers, resource names, data sources, attributes, and more.
* Code Navigation: Allows you to easily navigate through code by jumping to definitions, references, and symbols.
* Code Formatting: Formats your code with terraform fmt automatically.
* Module Explorer: Displays all modules and providers referenced in the currently open document.
* Terraform Commands: Allows you to directly execute commands like terraform init or terraform plan from the VS Code Command Palette 

[HashiCorp Terraform](https://marketplace.visualstudio.com/items?itemName=HashiCorp.terraform)
<br>
<img src="https://hashicorp.gallerycdn.vsassets.io/extensions/hashicorp/terraform/2.29.2023121311/1702465185067/Microsoft.VisualStudio.Services.Icons.Default" alt="drawing" width="50"/>

## Indent-Rainbow
The indent-rainbow module is a Visual Studio Code extension that colorizes the indentation in front of your text, alternating four different colors on each step. This can help make indentation more readable and can be helpful in writing code for Python, Nim, Yaml, and probably even filetypes that are not indentation dependent.

The extension uses the current editor window tab size and can handle mixed tab + spaces (not recommended). In addition, it visibly marks lines where the indentation is not a multiple of the tab size. The visualization can help to find problems with the indentation in some situations.

[Indent-Rainbow](https://marketplace.visualstudio.com/items?itemName=oderwat.indent-rainbow)
<br>
<img src="https://oderwat.gallerycdn.vsassets.io/extensions/oderwat/indent-rainbow/8.3.1/1649543509070/Microsoft.VisualStudio.Services.Icons.Default" alt="drawing" width="50"/>

## Jinja
Jinja is a template engine for Python. It is used to generate dynamic HTML pages, emails, or other text-based documents. Visual Studio Code has several extensions that support Jinja templates, including syntax highlighting, snippets, and linting.

The Jinja extension for Visual Studio Code adds language colorization support for the Jinja template language to VS Code. You can install it from the Visual Studio Code Marketplace. 

[Jinja](https://marketplace.visualstudio.com/items?itemName=wholroyd.jinja)
<br>
<img src="https://wholroyd.gallerycdn.vsassets.io/extensions/wholroyd/jinja/0.0.8/1494339408424/Microsoft.VisualStudio.Services.Icons.Default" alt="drawing" width="50"/>

## JSON Tools
JSON Tools is a Visual Studio Code extension that provides several tools for manipulating JSON. With this extension, you can pretty-print or minify JSON files, convert JSON to XML, and validate JSON files against a schema. You can use the following keyboard shortcuts to access these features:

* Ctrl+Alt+M (Windows) or Cmd+Alt+M (macOS) to pretty-print JSON.
* Alt+M to minify JSON.
* Ctrl+Alt+X (Windows) or Cmd+Alt+X (macOS) to convert JSON to XML.
* Ctrl+Alt+V (Windows) or Cmd+Alt+V (macOS) to validate JSON against a schema.

[JSON Tools](https://marketplace.visualstudio.com/items?itemName=eriklynd.json-tools)
<br>
<img src="https://cdn.vsassets.io/v/M232_20231217.1/_content/Header/default_icon_128.png" alt="drawing" width="50"/>

## YAML
YAML Language Support by Red Hat is a Visual Studio Code extension that provides comprehensive YAML language support to Visual Studio Code, via the yaml-language-server, with built-in Kubernetes syntax support. The extension offers several features, including:

* YAML validation: Detects whether the entire file is valid YAML and detects errors such as node is not found, node has an invalid key node type, node has an invalid type, node is not a valid child node.
* Document outlining: Provides the document outlining of all completed nodes in the file.
* Auto completion: Auto completes on all commands. Scalar nodes autocomplete to schema’s defaults if they exist.
* Hover support: Hovering over a node shows description if provided by schema.
* Formatter: Allows for formatting the current file. On type formatting auto indent for array items.
* YAML version support: Starting from 1.0.0, the extension uses eemeli/yaml as the new YAML parser, which strictly enforces the specified YAML spec version. Default YAML spec version is 1.2, it can be changed with yaml.yamlVersion setting.

[YAML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml)
<br>
<img src="https://redhat.gallerycdn.vsassets.io/extensions/redhat/vscode-yaml/1.14.0/1689778154971/Microsoft.VisualStudio.Services.Icons.Default" alt="drawing" width="50"/>

## XML
The XML extension for Visual Studio Code provides a range of features for working with XML files. Some of the features include:

* XML Formatting: This feature allows you to format your XML files in a readable and consistent way.
* XML Tree View: This feature provides a tree view of your XML document, making it easier to navigate and understand the structure of your document.
* XPath Evaluation: This feature allows you to evaluate XPath expressions on your XML document.
* XQuery Linting: This feature provides linting for XQuery expressions in your XML document.
* XQuery Execution: This feature allows you to execute XQuery expressions on your XML document.
* XQuery Code Completion: This feature provides code completion for XQuery expressions in your XML document.

[XML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-xml)
<br>
<img src="https://redhat.gallerycdn.vsassets.io/extensions/redhat/vscode-xml/0.26.2023120208/1701504652380/Microsoft.VisualStudio.Services.Icons.Default" alt="drawing" width="50"/>

## Vscode-Icons
The vscode-icons extension for Visual Studio Code provides a range of features for working with icons in your code editor. Some of the features include:

* Icons for Files and Folders: This feature allows you to customize the icons for files and folders in your workspace. You can choose from a wide range of icons or even use your own custom icons.
* Icons for Language Extensions: This feature allows you to customize the icons for different language extensions in your workspace. You can choose from a wide range of icons or even use your own custom icons.
* Icons for File Types: This feature allows you to customize the icons for different file types in your workspace. You can choose from a wide range of icons or even use your own custom icons.
* Icons for Snippets: This feature allows you to customize the icons for different code snippets in your workspace. You can choose from a wide range of icons or even use your own custom icons.

[Vscode-Icons](https://marketplace.visualstudio.com/items?itemName=vscode-icons-team.vscode-icons)
<br>
<img src="https://vscode-icons-team.gallerycdn.vsassets.io/extensions/vscode-icons-team/vscode-icons/12.6.0/1697899327455/Microsoft.VisualStudio.Services.Icons.Default" alt="drawing" width="50"/>

## Spelling Checker
The Code Spell Checker extension for Visual Studio Code provides a range of features for working with spelling in your code editor. Some of the features include:

* Real-time Spell Checking: This feature allows you to check spelling in real-time and highlight typos with wavy underlines. It points out spelling errors with a wavy line and displays possible correct answers.
* Customizable Spell Check Rules: This feature allows you to customize the spell check rules to suit your needs.
* Spell Check for Multiple Languages: This feature allows you to spell check your code in multiple languages.
* Spell Check for Markdown: This feature allows you to spell check your Markdown files.
* Spell Check for Comments: This feature allows you to spell check your comments in your code.

[Spelling Checker](https://marketplace.visualstudio.com/items?itemName=BelkacemBerras.spellcheck)
<br>
<img src="https://belkacemberras.gallerycdn.vsassets.io/extensions/belkacemberras/spellcheck/0.0.1/1608628917098/Microsoft.VisualStudio.Services.Icons.Default" alt="drawing" width="50"/>

## Sort
he Sort Lines module in Visual Studio Code allows you to sort selected lines of code alphabetically. This can be useful when you want to organize your code in a specific order. You can access this module by selecting the lines you want to sort and then pressing F9 or by right-clicking and selecting Sort Lines from the context menu.

If you are looking to sort functions by name, you can use the Outline view in the Explorer panel. You can sort by various categories, including Type, to get all the functions together and they are alphabetical

[Sort](https://marketplace.visualstudio.com/items?itemName=henriiik.vscode-sort)
<br>
<img src="https://cdn.vsassets.io/v/M232_20231217.1/_content/Header/default_icon_128.png" alt="drawing" width="50"/>

## Prettier - Code formatter
Prettier - Code formatter is a Visual Studio Code extension that automatically formats your code to enforce a consistent style. It parses your code and reprints it with its own rules that take the maximum line length into account, wrapping code when necessary. This extension supports various languages such as JavaScript, TypeScript, Flow, JSX, JSON, CSS, SCSS, Less, HTML, Vue, Angular, Handlebars, Ember, Glimmer, GraphQL, Markdown, and YAML.

To use this extension, you can install it through the Visual Studio Code extensions marketplace or by running the command ext install esbenp.prettier-vscode in the Quick Open window (Ctrl+P) 1. Once installed, you can set it as the default formatter in your Visual Studio Code settings to ensure that it is used over other extensions you may have installed.

[Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
<br>
<img src="https://esbenp.gallerycdn.vsassets.io/extensions/esbenp/prettier-vscode/10.1.0/1690819498575/Microsoft.VisualStudio.Services.Icons.Default" alt="drawing" width="50"/>

## PowerShell
PowerShell is a task-based command-line shell and scripting language built on .NET that provides a powerful toolset for administrators on any platform. The Microsoft PowerShell extension for Visual Studio Code (VS Code) provides rich language support and capabilities such as syntax completions, definition tracking, and linting for PowerShell. The extension should work anywhere VS Code itself and PowerShell Core 7.2 or higher is supported.

With the PowerShell extension, you can edit PowerShell scripts and modules in Visual Studio Code, and use its debugging interface to debug your code. You can also use the extension to run selected PowerShell code in the current terminal using F8.

[PowerShell](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell)
<br>
<img src="https://ms-vscode.gallerycdn.vsassets.io/extensions/ms-vscode/powershell/2023.11.1/1701997669128/Microsoft.VisualStudio.Services.Icons.Default" alt="drawing" width="50"/>

## Live Share
Live Share is a Visual Studio Code extension that enables you to collaborate with others on the same codebase in real-time without having to share your entire development environment. You can share your code with a friend, classmate, or professor without the need to sync code or to configure the same development tools, settings, or environment.

When you share a collaborative session, the person you’re working with sees the context of the workspace in their editor. This means your classmate can read the code you shared without having to clone a repo or install any dependencies your code relies on. They can help you with your code in the Visual Studio Code environment that’s familiar to them. Each of you can open files, navigate, edit code, or highlight - and changes are instantly reflected. As you edit, you can see your classmate’s cursor, jump to the same location, and follow their actions. You can also debug together using VS Code’s debugging features, like hovers, locals and watches, the stack trace or the debug console. You are both able to set breakpoints and advance the debug cursor to step through the session.

[Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare)
<br>
<img src="https://ms-vsliveshare.gallerycdn.vsassets.io/extensions/ms-vsliveshare/vsliveshare/1.0.5900/1702065121177/Microsoft.VisualStudio.Services.Icons.Default" alt="drawing" width="50"/>

