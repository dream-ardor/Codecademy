Aliases<br>
You can set up aliases for your bash scripts within your .bashrc or .bash_profile file to allow calling your scripts without the full filename. For example, if we have our saycolors.sh script, we can alias it to the word saycolors using the following syntax:
```bash
alias saycolors='./saycolors.sh'
```
You can even add standard input arguments to your alias. For example, if we always want "green" to be included as the first input to saycolors, we could modify our alias to:
```bash
alias saycolors='./saycolors.sh "green"'
```

**Instructions:**
Our script is updated to take an argument for the number of times the user wants to be greeted:
```bash
./script.sh 5 #greets 5 times
```
Let's create an alias so that when you type greet3 in the terminal, our script greets you three times.

In your own environment, you could add this alias to your ~/.bashrc to make the alias active every time the terminal is started.

Here, just make the alias in the command line.

Test out your new alias!

**Solution:**
```bash
#!/bin/bash
first_greeting="Nice to meet you!"
later_greeting="How are you?"
greeting_occasion=0
greeting_limit=$1
alias greet3="./script.sh 3"
while [ $greeting_occasion -lt $greeting_limit ]
do
  if [ $greeting_occasion -lt 1 ]
  then
    echo $first_greeting
  else
    echo $later_greeting
  fi
  greeting_occasion=$((greeting_occasion + 1))
done
```
