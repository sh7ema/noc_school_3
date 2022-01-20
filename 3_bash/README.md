Exit codes & Conditionals:
-1) Write a shell script that displays "This script will exit with a 0 exit status." Make sure that the script does indeed exit with a 0 exit
status

>!#/bin/bash
> 
> date
> 
> status=$?
> 
> echo "the date command exit status : ${status}"

2. Write a shell script that accepts a file or directory name as an argument. Have the script report if it is a regular file, a directory, or other type of file. If it is a regular file, exit with a 0 exit status. If it is a directory, exit with a 1 exit status. If it is some other
type of file, exit with a 2 exit status

>#!/bin/bash
>
>PASSED=$1
>
>if [[ -d $PASSED ]]; then
>
>    echo "$PASSED is a directory"
>
>    exit 1
>
>elif [[ -f $PASSED ]]; then
>
>    echo "$PASSED is a file"
>
>    exit 0
>
>else
>
>    echo "$PASSED is not valid"
>
>    exit 2
>
>fi


3. Write a script that executes the command "cat /etc/shadow". If the command returns a 0 exit status report "Command succeeded" and exit with a 0 exit status. If the command returns a non zero exit status report "Command failed" and exit with a 1 exit status

>#!/bin/bash
>
>#Redirect output to nowhere
>
>cat /etc/shadow > /dev/null 2>&1
>
>if [[ $? == 0 ]]; then
>
>   echo "Command succeeded"
>
>else
>
>   echo "Command failed"
>
>fi


4. Write a shell script to check to see if the file "/etc/shadow" exists. If it does exist, display"Shadow passwords are enabled. "Next, check to see if you can write to the file. If you can,display "You have permissions to edit /etc/shadow." If you cannot, display "You do NOT have permissions to edit /etc/shadow."