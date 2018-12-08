ENVIRONMENT<br>
Generalizations<br>

Congratulations! You learned to use the bash profile to configure the environment. What can we generalize so far?

The environment refers to the preferences and settings of the current user.
The nano editor is a command line text editor used to configure the environment.

~/.bash_profile is where environment settings are stored. You can edit this file with nano.

environment variables are variables that can be used across commands and programs and hold information about the environment.

* export VARIABLE="Value" sets and exports an environment variable.
* USER is the name of the current user.
* PS1 is the command prompt.
* HOME is the home directory. It is usually not customized.
* PATH returns a colon separated list of file paths. It is customized in advanced cases.
* env returns a list of environment variables.
