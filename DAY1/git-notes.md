# Git

Git allows you to back up, share and version control your work

GitHub is an online graphical user interface (GUI) for git

A repository or “repo” is a place you store all your code, files, etc. for a project

Forking - this allows you to create a copy of someone else’s repository on your own GitHub account and make changes freely. If you would like to make changes to the original repository you can submit a “pull request” to the author which they can approve

Cloning - when you clone a repository you create a copy on your local machine. You use `git clone <http url>` to clone a repository

`git add <file(s)>` will register the selected files with your git repo locally if they haven’t already been and then ‘stage’ them to be committed. You can think of this as adding the files to a staging area. You can stage all the files/directories within the current directory with `git add .`

Run `git status` on your local machine to get information on which files are staged

Run `git commit -m "<message>"` to commit your changes locally. It is good practice to commit changes frequently - ideally at least once a day

Branches allow you to work alongside others:

![image.png](attachment:0e91beaf-e9dd-45c3-b9ff-5a291b3338b3:image.png)

To create a new branch run `git checkout -b <new branch>` and to change branch run `git checkout <branch>`

Run `git push origin <branch>` to push your committed changes to github on the specified branch

You can use VS code’s Source Control tab in the left panel to access git’s features in a more graphical way

Whenever you start a project, create a git repository for it and practice regularly committing and pushing your changes

`git status`
`git add .`
`git commit -m ""`
`git push origin main`

`git stash`

