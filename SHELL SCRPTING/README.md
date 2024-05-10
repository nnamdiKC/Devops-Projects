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

**Example 5**: Using backtick for command substitution.

    current_date=`date +%Y-%m-%d`

**Example 6**: Using '$()' sytax for command substitution.

    current_date=$(date +%Y-%m-%d)


## 4. Input and Output
Bash provides various ways to handle input and output. You can use the read command to accept user input and the echo command to output text to the console. Additionally, inputs and outputs can be redirected using operators like 

    '> (output to a file)'

    '< (input from a file)'

    '| (pipe the output of one command as input to another)'

**Example 7**: Accept user input

    'echo "Enter your name"'
    read name

**Example 8**: Output text to the terminal

    'echo "Hello World"'

**Example 9**: Output the result of a command into a file

    'echo "Hello World" > index.txt'

**Example 10**: Pass the content of a file as input to a command

    'grep "pattern" < input.txt'

**Example 11**: Pass the result of a command as input to another command

    'echo Hello World" | grep "pattern"'


## 5. Functions
Functions can be used in Bash to group related commands together. They provide a way to modularize your code and make it more reusable. You can define functions using the function keyword or by declaring the function name followed by parenthesis.

    '#!/bin/bash

    # Define a function to greet the user
    greet() {
        echo "Hello, $1! Nice to meet you."
    }

    # Call the greet function and pass the name as an argument
    greet "John"



### Let's Write Our First Shell Script

**Step 1**: Create a folder called shell-scripting using the command 'mkdir shell-scripting' which will hold all our scripts.

**Step 2**: create a file called user-input.sh using the command touch user-input.sh

![alt text](<Images/shellscripting folder.png>)

**Step 3**: Enter the following lines of code in the file.
    
    #!/bin/bash

    # Prompt the user for their name
    echo "Enter your name:"
    read name

    # Display a greeting with the entered name
    echo "Hello, $name! Nice to meet you."

This script prompts for your name and displays the text *hello! Nice to meet you* after you have entered your name.

'#!/bin/bash' specifies the type of bash interpreter to be used to execute the script.

![alt text](<Images/user-input script.png>)

**Step 4**: save your file

**Step 5**: Run the command 'sudo chmod +x user-input.sh' this makes the file executable.

**Step 6**: Run the script using the command './user-input.sh'

![alt text](<Images/user-input result1.png>)



### Directory Manipulation and Navigation

This is simply writing codes in shell to perform same tasks of File/directory manipulation and navigation done in Linux file system.

This script will do the following:

    display the current directory

    create a new directory called "my_directory"

    change to the new directory, create 2 files inside it and list the files

    move back one level up

    remove "my_directory" and its contents

    and finally list the files in the current directory again'

Here goes the script:

    #!/bin/bash

    # Display current directory
    echo "Current directory: $PWD"

    # Create a new directory
    echo "Creating a new directory..."
    mkdir my_directory
    echo "New directory created."

    # Change to the new directory
    echo "Changing to the new directory..."
    cd my_directory
    echo "Current directory: $PWD"

    # Create some files
    echo "Creating files..."
    touch file1.txt
    touch file2.txt
    echo "Files created."

    # List the files in the current directory
    echo "Files in the current directory:"
    ls

    # Move one level up
    echo "Moving one level up..."
    cd ..
    echo "Current directory: $PWD"

    # Remove the new directory and its contents
    echo "Removing the new directory..."
    rm -rf my_directory
    echo "Directory removed."

    # List the files in the current directory again
    echo "Files in the current directory:"
    ls

![alt text](<Images/nav-linux-filesystem script.png>)

![alt text](<Images/nav-linux-filesystem result1.png>)


