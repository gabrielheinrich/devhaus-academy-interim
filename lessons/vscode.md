# VS Code: The software development toolkit

## Software Development Setup

### File Explorer

Keep an overview of the repository

### Code Editor

Write and edit individual source code files

### Terminal

Run commands to start your application, create or manipulate files,
download and install source code libraries and trigger a build process
(compilation)

### Debugger & Running Application

For manual testing and to debug your application

## VS Code UI Tour

- Editor (main window)
- Sidebar (left or right)
  - File Explorer
  - Search
  - Git Version Control
  - Debugger
  - Extensions
- Panel (bottom)
  - Terminal
  - Debug Console
  - Output
  - Problems
- Status Bar (very bottom)
  - Language Mode
  - Encoding
- Command Palette (overlay popup) (Win: Ctrl+Shift+P, Linux: Cmd+Shift+P)

## Keyboard vs Mouse

What are the differences between using a mouse vs. keyboard?

What are the advantages of using the keyboard to perform a specific action over
using the mouse? 

When is it better to use the mouse and when is it better to use
the keyboard? 

## Keyboard Shortcuts

### Key Modifiers

- Command (Mac)
- Option (Mac) / Alt (Win)
- Control (Win & Mac)

As a guideline most key commands which work with the command key on mac, work
with control on windows.

Sometimes you will find commands that are mapped to **key sequences**. These are
two keyboard shortcuts that have to be executed immediately after each other to
trigger a command, e.g. Ctrl+K Ctrl+O to open a directory from your file explorer.

## Opening Folders

In contrast to other programs like Microsoft Word, VS Code is not made to open individual files. Instead it is meant to open repositories, i.e. an entire directory/folder.

Naming Confusion: **Folder vs. Directory vs. Repository**

A **directory** is a location in a file system, like /bin or /home. 
A **repository** is a directory that is abunch of version controlled files.
A **folder** is..well, any folder.

You will often hear those terms interchangeably, and they basically mean the same thing. Usually a developers directories are version controlled. Thus, the term **repository** or short **repo** is used most often.

You can always quickly open new VS Code windows with different folders from your Terminal.

## Summary

VS Code is a very minimal but powerful central hub for an efficent software
development workflow. It integrates all essential tools needed for software
development in a way that stays true to their original form.

Mastering VS Code will greatly improve the speed and ease you can reach while
developing software.

We should be aiming to rely as little as possible on the mouse while
developing software.

Essential Rule for when you can't remember a specific keyboard shortcut: 
**Always try to use to the Command Palette before you reach for your mouse.**

It's important to keep track of all the source code repositories on your system.
One way to do so is to create a subdirectory in your user home directory called
**Developer**, which contains all your repositories.

## Exercises

- Tryout the keyboard shortcuts from the welcome page
- Use the command palette to change your color scheme. For more customization, check out this [list of themes](https://dev.to/thegeoffstevens/50-vs-code-themes-for-2020-45cc)
- Install the prettier code extension
- Create a Developer folder in your home directory
- Create a new repository called `developer-wiki`, open it in VS code and add some files, e.g. .txt for simple text files or .md if you already know Markdown 
  - If you are already familiar with the Command Line, create the folder and files using the `mkdir` and `touch` commands
(- Create a dock / task bar entry for VS Code, so you can open it quickly.)
- Change the default tab size in VSCode to 2 spaces through the **Workspace Settings** panel.
- Open **Workspace Settings as JSON** using the command palette and add this line to
  enable word-wrapping. 
  ```json
    "editor.wordWrap": "on",
  ```
  In this area you are able to add custom settings that might be needed for extension or customizing your developer experience (custom wrapping, display information about function on hover) for different languages you code in.

## Check Questions

- Can you name the essential tools necessary for software development and
  explain what their job is?
- What rule can you follow to make sure your keyboard shortcut repertoire in VS
  Code will constantly grow? Think outside of the box
- What is the purpose of the Developer folder?
- Why do we use VS Code to open entire folders instead of individual files?
- How can you check which folder is currently opened in VS Code?
- How can you lookup a keyboard shortcut in VS Code?
- What's the best method to quickly open a file within VS Code?

## Open Exercises

- Train to move through the VS Code window without moving the mouse.
  - Open and close the side bar.
  - Open the explorer
  - Open a file in the repository
  - Jump to the editor
  - Close the editor window
  - Open another file
  - Open the terminal
  - Jump back to the explorer
  - Jump to the editor
- Write your own personal list of important keyboard shortcuts in the
  `developer-wiki`
- Go on the hunt for some nice extensions. Create another entry in your
  developer wiki, where you keep track of your favorite vscode extensions.
- Train touch typing with [Tipp10](https://www.tipp10.com/de/) (highly recommended by your instructor Sven) or [Typing Club](https://www.typingclub.com/)
- Add more notes in your developer wiki. Create individual files for each topic like *extensions*, *settings*, *shortcuts*


## Resources

- [Windows Cheatsheet](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf)
- [macOS Cheatsheet](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-macos.pdf)
- [Linux Cheatsheet](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf)
