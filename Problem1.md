# Problem 1
The objectives of this problem are:
1. Figure out how to log in to the Linux virtual machine
via FastX.
2. Set up your Linux space 

## Linux via FastX
1. Go to https://fastx.divms.uiowa.edu
2. Log in with your HawkID and password.
3. Start a new session by clicking the `+` button on the 
top left, and launch a `MATE` session.
4. If successful, you can see your virtual desktop where
you will create your class directory.
5. Open up a command line terminal either through
`Applications -> MATE Terminal` (top left of the screen)
or by using the shortcut icon in the navigation bar on top. The terminal is always in some directory in your
Linux directory structure on the terminal. This
is called the *working directory* and is printed
before the command prompt (the `%` symbol). You can also
check which directory you are in using `pwd`
(for "print working directory"), and
you can change to a particular directory 
using `cd`. When you open the terminal, you should
be in your home directory within which your 
desktop is located. Move to your desktop by 
running:
    ```
    cd Desktop
    ```
6. Now create a directory for the class called `cs3210`
using mkdir:
    ```
    mkdir cs3210
    ```
7. Move into `cs3210` and check the current location
by running the following commands and record the output of the latter.
    ```
    cd cs3210
    pwd
    ```
8. The terminal can be used to open programs installed on the system and also to query them in various ways. 
You should already have a C++ compiler `g++`, the
VSCode IDE, and git installed on your system. To 
make sure, run the following commands and record all the outputs.
    ```
    g++ --version
    code --version
    git --version
    ```

# Command-Line Cheatsheet
1. `pwd` or "print working directory" prints the full path of the current directory of the terminal.
2. `cd <directory>` lets you "change directory" to `<directory>` directory. Two noteworthy shortcuts for directory paths: `.` refers to the current directory and `..` refers to the parent directory.
3. `ls` "lists" the directories and files contained within the current directory.
4. `mkdir <directory>` creates directory `<directory>` within the current directory.
5. `rm <file>` removes the argument file.
6. `rm -r <directory>` remvoves the argument directory, 
where `-r` is an *option* that modifies the behavior of the `rm` command to work on directories.