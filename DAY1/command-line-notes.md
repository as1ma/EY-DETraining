# Command Line

source: https://www.freecodecamp.org/news/command-line-for-beginners/#heading-most-common-and-useful-commands-to-use

Command line, shell & terminal have subtly different meanings but can essentially be used interchangably to refer to the same thing

WARNING! Be careful when using command line commands, especially ones that delete data - you don’t get the same warnings as you do with Finder/Windows Explorer.

`echo` - prints whatever parameter we pass to it to the terminal

`pwd` - print working directory (directory = folder)

`ls` - lists the contents of the current directory. Use `ls -a` to list hidden files (files that start with `.`)

`mkdir` - make directory. E.g., `mkdir test-directory` creates the directory “test-directory” within the working directory (run `ls` to verify this)

`rmdir` - remove directory. E.g., `rmdir test-directory` would remove the directory you just made (run `ls` to verify this). This only works on empty directories - removing directories with files/other directories in them is a little more complex

`touch` - creates an empty file in your working directory e.g., `touch test.txt` would create a new text file

`rm` - deletes a file e.g., `rm test.txt` would remove your new test.txt file. 

`cd` - change directory. For example if your documents have a “test” directory and you are in documents, `cd test` will change your working directory to `test`

`cd ..` changes your directory to the parent directory

`cd ~` should take you to your user folder and `cd /` should take you to your root folder (the root folder is the ultimate parent folder)

`cp` - copies a file/directory to another location. For example, if you had a `test` folder and a `test.txt` file in your working directory, running `cp test.txt test` would move `test.txt` into `test`

`mv` - moves the file/directory instead of copying it (the equivalent of cut/paste)

`ctrl + c` will exit the current process - you will need to use `ctrl + shift + c` to copy depending on your OS

`clear` clears your terminal

`--help` - this option can be used on most commands and will tell you how to use the given command

`cat` - prints a file to the terminal (e.g., `cat test.txt`)

`nano/vi` - these are text editors for the command line. `nano` is more intuitive for beginners but less powerful. We will mostly be using VS code as our text editor anyway so don’t worry about these. If you accidentally get stuck in VI, type `:q` and hit enter and it should take you out of it

`sudo` - short for “superuser do”. This basically gives you admin privileges on a command where you need special permissions. It will require you to enter your password (unless you ran another `sudo` command recently). This is only for Linux and Mac

The tab key can be used to autofill files/directories

A command takes the general syntax `command [flags/parameters/options] [operands]`

- The command is mandatory. It is the name of a program, script or executable file
- The flags/parameters/options are optional and often preceded by a `-` or `--`. They change the commands functionality
- The operands are optional. They are the files or data the command will operate on

The command line is more powerful than you might think. Check out some of these projects:

- https://www.youtube.com/watch?v=J9Exjbotz6g
- https://www.youtube.com/watch?v=YmzBJmpFMpw

Exercises:

- Navigate to your Documents folder using command line.
- Create a new text file called ‘test.txt’
- Verify the file was created
- Create a folder called “test-folder”
- add some text to your test.txt file only using command line
- Verify text was added
- Move the test.txt file into the test-folder folder
- Navigate into the test folder
- Verify the folder was moved
- Move the test.txt file back into Documents
- Verify it was moved again

Stretch challenges:

- Navigate to Documents and create a new folder “new-folder” within test-folder from Documents (do not cd into test-folder)
- Still from within documents, list the files in test-folder to check it was created
- cd into your new “new-folder”
- move test.txt into the new folder

[Back](links.md)