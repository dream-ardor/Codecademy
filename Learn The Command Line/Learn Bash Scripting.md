Introduction to Bash Scripting<br>

Bash (or shell) scripting is a way to automate tasks that execute within a Bash shell interpreter terminal. Any command you can run in your terminal can be run in a Bash script. When you have a command or set of commands that you will be using frequently, consider writing a Bash script to perform it.

There are some conventions to follow to ensure that your computer is able to find and execute your Bash scripts. The beginning of your script file should start with #!/bin/bash on its own line. This tells the computer which type of interpreter to use for the script. When saving the script file, it is good practice to place commonly used scripts in the ~/bin/ directory.

Your terminal runs a file every time it is opened to load its configuration. On Linux style shells, this is ~/.bashrc and on OSX, this is ~/.bash_profile. To ensure that scripts in ~/bin/ are available, you must add this directory to your PATH within your configuration file:
```bash
PATH=~/bin:$PATH
```
Now any scripts in the ~/bin directory can be run from anywhere by typing the filename.

