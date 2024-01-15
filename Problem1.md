# Problem 1
The objectives of this problem are:
1. Figure out how to log in to the Linux virtual machine via FastX.
2. Set up your Linux directory space for class
**Please note** that you will need to record some outputs in a file called `solutions.csv` from the commands you run in this problem. However, you won't be able to do this until you finish the tasks in [Problem 2](./Problem2.md). You still have to finish the non-recording tasks in this problem before you can complete the tasks from problem 2. So essentially, your order 
will be Problem 1 (create directory structure) -> Problem 2 (set up git) -> Problem 1 (record outputs) -> 
Problem 2 (push recorded outputs) -> Problem 3 (record and push).

## Linux via FastX
1. Go to https://fastx.divms.uiowa.edu
2. Log in with your HawkID and password.
3. Start a new session by clicking the `+` button on the top left, and launch a `MATE` session.
4. If successful, you can see your virtual desktop where you will create your class direct*ory.
5. Open up a command line terminal either through 
 `Applications -> MATE Terminal` (top left of the screen), or by using the shortcut icon in the navigation bar on top, or by
the keyboard shortcut `Ctrl + Alt + t`. The terminal is always in some directory in your Linux directory structure on the 
terminal. This is called the *working directory* and is printed before the command prompt (the `%` symbol). You can also
check which directory you are in using `pwd` (for "print working directory"), and you can change to a particular directory 
using `cd`. When you open the terminal, you should be in your home directory within which your desktop is located. 
Move to your desktop by running:
    ```
    cd Desktop
    ```
6. Now create a directory for the class called `cs3210` using mkdir:
    ```
    mkdir cs3210
    ```
7. Move into `cs3210` and check the current working directory by running the following commands and 
record the output of the latter in the solution column of row `1a` in [solutions.csv](./solutions.csv).
    ```
    cd cs3210
    pwd
    ```
8. The terminal can be used to open programs installed on the system and also to query them in various ways. 
You should already have a C++ compiler `g++`, the VSCode IDE, and git installed on your system. To 
make sure, run the following commands and record each 
of the outputs as 1b, 1c, and 1d, respectively.
    ```
    g++ --version
    code --version
    git --version
    ```
9. Now open vscode and open the `cs3210` directory through `File -> Open Folder` and then navigating to the folder and 
selecting it (via the GUI). Now you have the vscode IDE opened up and your workspace set up to the cs3210 directory.
As you add more stuff to this directory from Github, you will be able to navigate and edit the files from vscode.

# Command-Line Cheatsheet
1. `pwd` or "print working directory" prints the full path of the current directory of the terminal.
2. `cd <directory>` lets you "change directory" to `<directory>` directory. Two noteworthy shortcuts for directory paths: `.` refers to the current directory and `..` refers to the parent directory.
3. `ls` "lists" the directories and files contained within the current directory.
4. `mkdir <directory>` creates directory `<directory>` within the current directory.
5. `rm <file>` removes the argument file.
6. `rm -r <directory>` remvoves the argument directory, 
where `-r` is an *option* that modifies the behavior of the `rm` command to work on directories.