# Github-Usefull-Command

- 🌱 Setting up name and e-mail address --> If you've never used git before, first you need to set up your name and e-mail. Run the following commands to let git know your name and e-mail address. If git is already installed, skip down to the end of the line. 

git config --global user.name "Your Name"
 
git config --global user.email "your_email@whatever.com" @@

 

Installation Options line endings 

Also, for users of Unix/Mac: 

git config --global core.autocrlf input 
 

git config --global core.safecrlf warn 

For Windows users: 

git config --global core.autocrlf true 
 

git config --global core.safecrlf warn 

 

1. git clone  --> used for downloading the latest version of a remote project and copying it to the selected location on the local machine. 

git clone <repository url> 

 

To clone a specific branch, you can use 

git clone <repository url> -b <branch name> 

 

2. git fetch  --> This Git command will get all the updates from the remote repository, including new branches. 

 

3. git checkout --> You can use the checkout command to switch the branch that you are currently working on. 

git checkout <branch name> 

If you want to create a new branch and switch to it, you can do it by using this command: 

git checkout -b <branch name> 

 

4. git init --> if you want to start a new empty repository or to reinitialize an existing one. It will create a .git directory with its subdirectories. 

git init <repository name> 

 

5. git commit --> To create a new commit. 

git commit -m "<commit message>" 

 

6. git push --> Git push will push the locally committed changes to the remote branch. 

git push 

 

If the branch is not yet tracked, and only resides on the local machine, you need to run the command like this: 

git push --set-upstream <remote branch> <branch name> 

 

7. git diff --> If you want to see the staged changes, run the diff command like this: 

git diff --staged 

Or you can compare two branches: 

gif diff <branch1> <branch2> 

 

8. git pull --> Using git pull will fetch all the changes from the remote repository and merge any remote changes in the current local branch. 

 

9. git add --> This is the command you need to use to stage changed files. You can stage individual files: 

git add <file path> 

Or all files: 

git add . 

 

10. git branch --> you can use it to create a new branch, without checking it out: 

git branch <new branch> 

To delete a branch, run it like this: 

git branch -d <branch name> 

 

11. git status --> Use the command, to check the current state of the repository.  

 

git status 

 

This means that git knows about the change, but it is not permanent in the repository. The next commit will include the changes staged. 

Should you decide not to commit the change, the status command will remind you that you can use the git reset command to unstage these changes. 

12. git History --> To learn to view the project’s history. Getting a list of changes made is a function of the git log command. 

 

git log 

 

One line history 

You fully control what the log shows. I like the single line format: 

 

git log --pretty=oneline 

 

Controlling the display of entries 

There are many options to choose which entries appear in the log. Play around with the following parameters: 

git log --pretty=oneline --max-count=2 
 

git log --pretty=oneline --since='5 minutes ago' 
 

git log --pretty=oneline --until='5 minutes ago' 
 

git log --pretty=oneline --author=<your name> 
 

git log --pretty=oneline –all 

 

Getting fancy 

This is what I use to review the changes made within the last week. I will add --author=alex if I want to see only the changes made by me. 

 

git log --all --pretty=format:"%h %cd %s (%an)" --since='7 days ago' 

 

The ultimate format of the log 

Over time, I found the following log format to be the most suitable. 

 

git log --pretty=format:"%h %ad | %s%d [%an]" --graph --date=short 

 

Let’s look at it in detail: 

--pretty="..." defines the output format. 

%h is the abbreviated hash of the commit 

%d commit decorations (e.g. branch heads or tags) 

%ad is the commit date 

%s is the comment 

%an is the name of the author 

--graph tells git to display the commit tree in the form of an ASCII graph layout 

--date=short keeps the date format short and nice 

So, every time you want to see a log, you'll have to do a lot of typing. Fortunately, we will find out about the git aliases in the next lesson. 
