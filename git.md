# Git

## Git Links
| Purpose                                                    | URL                                                                                         |
|------------------------------------------------------------|---------------------------------------------------------------------------------------------|
| Cache Git Password for easy pushing                        | https://help.github.com/articles/set-up-git/#next-steps-authenticating-with-github-from-git |
| Checkout local copies of pull requests from GitHub remotes | https://gist.github.com/gnarf/5406589                                                       |
| Checkout branch on a fork                                  | https://help.github.com/articles/configuring-a-remote-for-a-fork/                           |
| Commonly used commands                                  | https://github.com/git-tips/tips                           |
| Interactive Tutorial: Learn Git Branching  | http://learngitbranching.js.org/ |


## Git Glossary
| Term                 | Meaning                                                                                                    |
|----------------------|------------------------------------------------------------------------------------------------------------|
| Working Directory    | Files that are currently being worked on (or checked out)                                                  |
| Index (staging area) | Files that have been prepped for a commit                                                                  |
| Commit               | A group of files, accompanied by a descriptive message, that are going to be pushed to the repo eventually |


## Common Git Commands

Create a new local branch based off the current branch

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git checkout -b <branch-name>`  | None  | None       |

<br>
Create a new local branch based off another branch

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git branch <new-branch> <old-branch>`  | None  | None       |

<br>
Create a remote branch based on the current branch

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git push <remote-name> <branch-name>`  | None  | None       |

<br>
Rename a local branch

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git branch -m <oldname> <newname>`  | Use if you're renaming a branch you're not on  | None       |
| `git branch -m <newname>`  | Use if you're on the branch  | None       |

<br>
Delete a local branch

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git branch -d <branch-name>`  | None  | None       |

<br>
Delete a remote branch

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git push origin :<branch-name>`  | None  | None       |

<br>
Show all local branches and their tracking information

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git branch -vv`  | None  | None       |

<br>
Stop tracking a remote branch

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git branch --unset-upstream`  | None  | None       |

<br>
Pull a remote branch

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git fetch && git checkout <branch-name>`  | None  | None       |

<br>
Find the commit where a bug was introduced (Need a commit hash of when it works and when it doesnt work)

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git bisect start` - Start git bisect operations<br>`git bisect good master` - Commit hash where the problem is not occurring<br>`git bisect bad 50a2ea02` - Commit hash where the problem is occurring<br><br>As each commit is checked out, test for it and tell git if it is occurring or not<br>`git bisect good` - Problem is not occurring<br>`git bisect bad` - Problem is occurring<br>`git reset` - Terminate git bisect operations   | Detailed Instructions: http://webchick.net/node/99  | None       |

<br>
Find the commit where a bug was fixed (Need a commit hash of when it works and when it doesnt work)

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git bisect start` - Start git bisect operations<br>`git bisect bad master` - Commit hash where the problem is not occurring<br>`git bisect good 50a2ea02` - Commit hash where the problem is occurring<br><br>As each commit is checked out, test for it and tell git if it is occurring or not<br>`git bisect good` - Problem is occurring<br>`git bisect bad` - Problem is not occurring<br>`git reset` - Terminates git bisect operations   | The idea is to reverse the process of git bisect and tell it that it is `good` when it doesn't work and it is `bad` when it does work.<br><br>Detailed Instructions: http://stackoverflow.com/a/15407206/83916  | None       |

<br>
View the latest commits in the repo

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git log`  | None  | None       |
| `git log --stat`  | The _--stat_ parameter specifies that each commit should display the names of the files that were changed  | None       |
| `git log -p`  | The _-p_ parameter specifies that each commit should display the full diff  | None       |

<br>
Add files to the staging area

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git add <filename with extension>`  | By specifying the specific filename, only that file will be added to the staging area  | None       |
| `git add -A`  | The _-A_ parameter specifies that all tracked files will be added to the staging area	  | None       |
| `git add "*.txt"`  | The wildcard(*) character specifies that any file matching anything before the file extension will be added to the staging area  | None       |

<br>
Commit files to the repo

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git commit -m "Provide an informative commit message here"`  | Commits all staged files  | None       |
| `git commit -a -m "Provide an informative commit message here"`  | Stages all tracked files and commits them  | None       |
| `git commit --amend -m "New commit message"`  | Add all staged files to the previous commit and override the previous commit message with a new one (optional)  | None       |
| `git commit --amend --no-edit` <br> `git push -f origin <branch name>`  | Make changes to the last commit and force push the changes to the remote repo. This will overwrite the history so it appears as if the latest change was there in the last commit.  | None       |--no-edit

<br>
Check the line differences of files in various stages of development

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git diff`  | Show differences between the working directory and the staging area  | None       |
| `git diff --staged`  | Show differences between the staging area and the most recent commit  | None       |
| `git diff HEAD`  | Show differences between the working directory and the most recent commit  | None       |

<br>
Unstage files

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git reset HEAD <filename with extension>`  | Remove the specified file from the staging area  | None       |
| `git reset --soft HEAD^`  | Undo last commit and move files back to staging  | None       |
| `git reset --hard HEAD^`  | Undo last commit and remove all changes  | None       |
| `git reset --hard HEAD^^`  | Undo last two commits and remove all changes  | None       |

<br>
Associate an alias with a remote repo URL

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git remote add <remote-name> <repo-url>`  | Creates an alias which tells Git that the remote-name specified relates to the specified Git repo URL<br>Example: `git remote add origin https://github.com/example/example-repo.git`   | None       |
| `git remote -v`  | List all remote repos available and their alias  | None       |

<br>
Get help

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git help`  | Displays a list of common git commands  | ![Example - git help] (https://github.com/zeckdude/code-references/blob/master/img/git/git_help_1.png)       |
| `git help <command name>`  | Displays detailed information about a specific git command and its parameters  | ![Example - git help <command name>] (https://github.com/zeckdude/code-references/blob/master/img/git/git_help_2.png)       |

<br>
Configure Git Settings

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git config --global user.name "Jim Bob"`  | Sets the name to record when committing changes  | None       |
| `git config --global user.email jim.bob@hotmail.com`  | Sets the email to record when comitting changes  | None       |
