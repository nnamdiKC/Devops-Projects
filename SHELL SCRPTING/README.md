#### INTRODUCTION TO SHELL SCRIPTING
Shell Scripting is a powerful tool that is used to automate tasks, test solutions and improve efficiency. A Shell script is a text file that contains a list of commands that instructs an operating system to perform certain tasks.

### Shell Scripting Syntax Elements

## 1. Variables
Variables can store data of various types such as numbers, strings and arrays. Values can be assigned to variables using the '=' operator and access their values using the variable name preceded by '$' sign.

Example: Assigning value to a variable

    'name="John"'

Retreiving value from a variable

    'echo $name'

## 2. Control Flow

Bash provides control flow statements like 'if-else' for loops, while loops and case statements to control the flow of execution in your scripts. These statements allow you make decisions, iterate over lists and execute different commands based on conditions.

Examples: Using *if-else* to execute script based on a condition

    #!/bin/bash

    # Example script to check if a number is positive, negative, or zero

    read -p "Enter a number: " num

    if [ $num -gt 0 ]; then
        echo "The number is positive."
    elif [ $num -lt 0 ]; then
        echo "The number is negative."
    else
        echo "The number is zero."
    fi

 