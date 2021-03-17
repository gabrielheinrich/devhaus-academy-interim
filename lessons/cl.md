# Intro to the Command Line

[Slides](https://docs.google.com/presentation/d/1LW8RSdda0dO7pJcTsWHDyzcr6YYCP5KbrUtjiimT0-4/edit?usp=sharing)

## Walkthrough 1 - Developer Routine

**SETUP**

Connecting to your personal docker container. A private space to store document in an environment that is perfectly setup for development (zsh, git etc.
)
1. Open VS Code
2. Open a Terminal
3. Add the extension Remote SSH.
4. Navigate to the new Remote Explorer tab in the left side bar.  Complete the setup steps by typing in the command `ssh user@[your-name].devhausleipzig.de`
5. Press the icon next to your container name to connect to the host in a new window

Alternatively you can reach your container by typing `ssh user@[your-name].devhausleipzig.de` into the command line

Perform the Developer Routine shown in the slide. 
If you already have a `Developer` folder, create a `dev` folder instead. This is just for demonstration purpose.

## Walkthrough 2 - Interacting with VS Code through your Command Line

For this part we will be using the `code` command. Check if you have it installed by typing `which code` into your command line. It should print something like `/bin/code`.

1. Open a Terminal
2. `cd` into your developer-wiki folder
3. Open it in VS Code by typing `code .`. The dot . means *current directoy*. Two dots .. means parent directory.
4. Did it open a new VS Code window? Now we don't want that mess. Type in the command `code --help`, and scroll through the documentation. In the list of `Options` read about out the `-r` flag. Close your folder in VS Code, in your command line `cd` into the directory you want to open and try the command `code . -r` command. It should open the folder in the same VS Code window.


## `cal` Command Exercises

Read the manual for the cal command and identify the needed flags/options to find the answer.

- Print out the calendar for the full current year.
- Find out what the difference between cal and ncal is.
- Find out which date easter was in 1803.
- Find out on which Gabe was born.
- Find out which day of the year we have today.
- Print the second half of this year as a calendar.

## Command Line Hacks

- To get the instruction for a specific command type `man [name-of-command]` into your command line
- a dot . means your current directory
- two dots .. means one folder structure above
- If you are inside vi/vim (a command line tool which is a minimalistic text editor) hit the **q** (quit) key to exit it

## Command Examples
- `mkdir [new-directory-name]`: create a new directory
- `touch [new-file-name]`: create a new file
- `ls`: lists files and folders of directory you are currently in
- `pwd`: prints the path from your home directory up until the directory you are in
- `cd [location]`: change directory
- `cat [filename]`: print file content to your command line (no kittens involved :( )
- `clear`: clears the command line
- `exit`: closes terminal
- `which [name-of-command]`: shows you where source of that command 
- `man [name-of-command]`: shows you the manual of a command

**Bonus Command**: 

`nc towel.blinkenlights.nl 23`

## Open Exercises
- Play a command line game like [CLMystery](https://github.com/veltman/clmystery) or [Terminus](http://web.mit.edu/mprat/Public/web/Terminus/Web/main.html)


## Cheat Sheet
- [Command Line Cheat Sheet](resources/command-line-cheat-sheet.png)