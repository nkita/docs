# What is the Commit Message Generator？  
The Commit Message Generator is a tool designed to assist in creating commit messages. Have you ever faced the following issues when creating commit messages or reviewing past commit logs?

* Inconsistent and unclear messages
* Different formats for each project
* Variability in scope naming
* Wanting to add emojis to make messages more expressive


To address these challenges, the Commit Message Generator was developed. While there are many excellent tools such as [commitizen](https://github.com/commitizen/cz-cli), [commit.template](https://git-scm.com/book/ja/v2/Git-%E3%81%AE%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%9E%E3%82%A4%E3%82%BA-Git-%E3%81%AE%E8%A8%AD%E5%AE%9A), [git-za](https://github.com/streamich/git-cz), and commit.template that serve as commit message formatters or assistive tools, our tool stands out in the following ways:

1. Easily accessible through a web interface.
2. No installation required.
3. Equipped with a feature to remember past input content for reuse.

Furthermore, in this tool, login is not required for ease of use, and all settings are stored within the browser for privacy and convenience.

# Usage
A commit message Generator has two modes: generate mode and customization mode.

## ⚡Generate Mode
![Generate Mode](https://shiba-tools.dev/usage01.png)
This is the default mode (the initial screen when accessed).
You can create commit messages in a format aligned with templates. 
To use it, simply input the relevant information into the input form on the left side of the screen, and the formatted commit message will appear in the output area on the right side.

You can select a template from the 'Select Template' option in the top right corner, or create a new original template.

## ⚡Customize Mode
![Customize Mode](http://shiba-tools.dev/usage02.png)
In Customize Mode, you have the freedom to create templates according to your needs for the commit message creation mode. Currently, the following items are customizable:

### Title
You can change the template name in the title. For example, if the commit message format varies by project, it would be helpful to include the project name directly in the title for clarity.

### Description 
You can modify the description text of the template. The description text supports Markdown format, allowing for clear and expressive formatting such as headings and links.
Please include any important points or instructions for using the template in this description.

### Forms

The input form refers to the form used in the commit message creation mode for creating commit messages. The following items are included:
* Type
* Summary
* Scope
* Body
* Footer


In the form customization, you have the ability to change the format of the fields. Below are descriptions of the formats used in the default template:
| Type | Description | Form|  
| :---- | :---- | :---- |  
| A line| This format is suitable for short, concise input, such as a summary or title.　| Summary|
| Multi-line| Use this format for entering detailed information, such as the body of the message or additional notes.| Body, Footer|
| Dropdown| This format allows you to select from predefined options. You can provide explanations for each option in the description.| Type|
| Dynamic Dropdown| With this format, input values are automatically saved for future use, reducing inconsistencies in input during subsequent commit message creation. | Scope|  
