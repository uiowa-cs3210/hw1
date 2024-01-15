# Problem 2
The objectives of this problem are:
1. Set up your local git repository in your `cs3210` directory
2. Push solutions from problems in this assignments.

## Git Setup
1. Log in to your remote Desktop using FastX (see [Problem1.md](./Problem1.md)).
2. Open a browser, and create a [Github](https:www.github.com) account if you don't already have one.
3. Create a Github PAT (personal access token) using the instructions from 
[here](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token-classic). Give it an expiration 
date that is after the end of the semester (unless you want to keep changing these for more security) 
and give it `repo` scope, so you can use it to maintain repositories locally. 
**Once created, save this PAT somewhere because you will have to use it to authenticate your Git account 
from the command line.**
4. Open your terminal and navigate to the `cs3210` on your Desktop (`~/Desktop/cs3210/`). You can
use `pwd` to check whether you are in the correct directory.
5. Create a repository called `homeworks`.
    ```
    mkdir homeworks
    ```
6. Now we are going to [clone](./README.md#octocat-cloning) the homework 1 repo into this directory. 
For this we need the repo's URL. You can find this in the home (web) page of the repo.
Your repo should be called `uiowa-cs3210-spr23/hw1-GITHANDLE` where `GITHANDLE` is a placeholder for your 
Github handle. At the homepage, click the green `<> Code ` button and under HTTPS you will find the URL 
which should look like:
    ```
    https://github.com/uiowa-cs3210-spr23/hw1-GITHANDLE.git
    ```
7. Copy this URL, and in your terminal, in the `homeworks` directory, run the command `git clone ` followed by 
the URL. Note that the keyboard shortcuts for copying (`Ctrl + c`) and pasting (`Ctrl + v`) don't work in 
the terminal so you have to do it through the mouse right click button. The command you run 
would look like the following:
    ```
    git clone https://github.com/uiowa-cs3210-spr23/hw1-GITHANDLE.git
    ```
    Note that you have to enter your Github username (handle) and PAT (not password) when prompted, 
    for authentication.
8. Make sure the repository has been cloned locally. Running `ls` on the terminal should show a `hw1-GITHANDLE` directory. 
Open up vscode and set the `cs3210` directory as your working directory if you haven't already, and you should see 
the `hw1` directory there as well (on the file navigation space on the left). 
A git directory is a regular directory in your file system initialized with some git files. You can check whether your directory is a git directory by navigating into it and running the `git remote` command.
    ```
    cd hw1-GITHANDLE
    git remote -v
    ```
    Record each line of the output as 2a and 2b. 
    The output should read:
    ```
    origin	https://github.com/uiowa-cs3210-spr23/hw1-GITHANDLE.git (fetch)
    origin	https://github.com/uiowa-cs3210-spr23/hw1-GITHANDLE.git (push)

    ```
    which is saying that your local directory is set up to track the remote repo in the URL (by fetching) and also that it can send updates to the same repo (by pushing).
9. Your local repo can either be (i) *ahead of*, (ii) *up to date with*, or (iii) *behind* the remote repo. You want to be 
able to verify each case. Git's `status` command can be used to check whether (i) or (ii) is the case. At this point, your
local repo should be up to date with the remote repo. Running the command should give you the commented output 
(comments are preceded by `#`):
   ```
   git status
   #On branch main
   #Your branch is up to date with 'origin/main'.
   #
   #nothing to commit, working tree clean
   ``` 
   This command will have a different output if your local repo is ahead of its remote counterpart.
   A more tedious way of checking whether your local repo is behind the remote one is by opening the remote
   repo by its webpage and checking its code against the code in your local repo (this method doesn't scale
   to larger projects). The more principled way of doing this is by *pulling* any possible changes from the remote 
   repo:
   ```
   git pull
   #Already up to date.
   ```
   The commented output is shown when it is the case that the remote repo isn't ahead of the local one.
   Otherwise, it would pull the changes into the local repo. For instance, I might make changes to the homework 
   specification which I might ask you to pull after you have already cloned the homework repo. Here I want to bring up 
   the possibility of the ever-annoying **merge conflicts**. A merge conflict occurs when local changes and 
   remote changes are incompatible. For example, suppose a text file contains the text `Hello World` and I change it to `Hello, World` and suppose that you change it locally to `HelloWorld` before you pull my changes. Now Github
   doesn't know whether it should override your local change (in which case it will be lost), or to 
   override the remote one (in which case we're not really pulling). It complains with a merge conflict. These are better 
   to prevent than fix. Some guidelines to prevent them:
   * Always `pull` before you `push`.
   * `pull` frequently.
   * Don't touch the problem specification files (and conversely, I will try not to touch the solution files).
   Since it will be only each of you coordinating your commits with me (as opposed to team members having to
   coordinate with other members in addition to the instructor), this should suffice. Typically I will try to push 
   the homework and then not push any more changes till your submissions are done (unless we find mistakes in the
   specification in which case I will have to push changes, but this shouldn't cause merge conflicts as long as you don't 
   make any changes to the specification files.)
10. Now we are ready to [push](./README.md#octocat-committing-and-pushing) our changes. Let's say you are ready to push your 
solutions from Problem 1 (come back here when you are). Running `git status` at this point should confirm that your local 
repo is ahead:
    ```
    git status
    #On branch main
    #Your branch is up to date with 'origin/main'.
    #
    #Changes not staged for commit:
    #(use "git add <file>..." to update what will be #committed)
    #(use "git restore <file>..." to discard changes in #working directory)
    #modified:   MODIFIEDFILENAME
    ```
    Where `MODIFIEDFILENAME` is a placeholder for a changed file. Now we can [commit](./README.md#octocat-committing-and-pushing) these changes with a meaningful message:
    ```
    git commit -a -m "Completed problem 1" 
    ```
    The `-a` option tells `git` to include all changed files in the commit (except newly added files which
    must be tracked using `git add`). And the `-m` option allows you to specify a string message to describe 
    the commit, which must follow the option. Now check the status (`git status`) and you will see that
    the commit is *staged* and ready to be pushed to the remote repo.
11. Finally, push the changes online by running:
    ```
    git push
    ```
    Once authenticated, git will let you know if it has successfully written to the remote files.