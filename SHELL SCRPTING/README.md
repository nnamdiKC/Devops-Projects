#### INTRODUCTION TO SHELL SCRIPTING
Shell Scripting is a powerful tool that is used to automate tasks, test solutions and improve efficiency. A Shell script is a text file that contains a list of commands that instructs an operating system to perform certain tasks.

### Shell Scripting Syntax Elements

## 1. Variables
Variables can store data of various types such as numbers, strings and arrays. Values can be assigned to variables using the '=' operator and access their values using the variable name preceded by '$' sign.

Example 1: Assigning value to a variable

    'name="John"'

Example 2: Retreiving value from a variable

    'echo $name'

## 2. Control Flow

Bash provides control flow statements like 'if-else' for loops, while loops and case statements to control the flow of execution in your scripts. These statements allow you make decisions, iterate over lists and execute different commands based on conditions.

Example 3: Using *if-else* to execute script based on a condition

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

![alt text](<Images/vi myscript.png>)

Run the script, it will respond with this request 'Enter a number', you are to enter any number of your choice. See the outcome below

![alt text](<Images/output for myscript.png>)


**Example 4**: Iterating through a list using a *for loop*

For this example, let us create another script; call it "forloop.sh" that will allow printing numbers 1 - 5.


#!/bin/bash

#Example script to print numbers from 1 to 5 using a for loop

    for (( i=1; i<=5; i++ ))
    do
        echo $i
    done

![alt text](<Images/vi forloop.png>)

Run the script using this command *'./forloop.sh'*

The result is

![alt text](<Images/result forloop.png>)


## 3. Command Substitution
Command substitution allows you to capture the output of a command and use it as a value within your script. You can use the backtick or the $()syntax for command substitution.

**Example 5**: