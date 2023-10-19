# Personal Sublime Text Editor Setup 
This repo contains the files to my personal Sublime Text setup and the list of all the installed packages.  
  
```Version: Build 4113```
  
Table below shows the packages I found useful considering the fact the main purpose for using Sublime was finding the most efficient way to code in C / C++ / simple LaTeX notes / basic non-scientific Python.  


| Package Name  | Links to the Package Control website                   |
|---------------|--------------------------------------------------------|
| Terminus      | https://packagecontrol.io/packages/Terminus            |
| SideBarEnhanc | https://packagecontrol.io/packages/SideBarEnhancements |
| FileIcons     | https://packagecontrol.io/packages/FileIcons           |
| C Improved    | https://packagecontrol.io/packages/C%20Improved        |
| SublimeLinter | https://packagecontrol.io/packages/SublimeLinter       |  
| PDSSnippets   | https://packagecontrol.io/packages/Python%20Data%20Science%20Snippets|  

## Guide to Installing Packages Manually
In order to install the mentioned instead of copying, press ```Ctrl+Shift+P``` button, select **Install Packages** and type the name for each package.  
## Update Check 
Having the latest version is not essential here, so we will have to turn them off using Settings in Preferences, and adding up the following bit to the right hand side:  
  
```"update_check": false```
  
This should fix the issue.  
## Font Preference
I use the font Cascadia Code by Microsoft, which is available through a simple search in their Github profile. In order to apply the font to Sublime Text, we head to Preferences, Settings and copy and paste the line of code below and restart the client assuming Cascadia Code is already installed on the computer.  
  
```c
"font_face":"Cascadia Code"
```
## Terminus Keybindings
In order to start Terminus, which manages to run command prompt within Sublime Text, in a working directory, we will need to setup the keybinding below:   
  
```c
[
    { 
        "keys": ["ctrl+alt+t"], "command": "terminus_open", "args": {
            "cwd": "${file_path:${folder}}"
        }
    }
]
```
## Creating a Build System with Terminus
Every build system in Sublime Text comes with a format .sublime-build, therefore a copy of C/C++ builder file is required which could be found via searching for vpf ( View Package Files ) . Add the two commands below in order to set Terminus up instead of default shell.  
```c
	"target": "terminus_exec",
	"cancel": "terminus_cancel_build",
```
