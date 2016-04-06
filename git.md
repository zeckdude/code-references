# Git

## Git Links
| Purpose                                                    | URL                                                                                         |
|------------------------------------------------------------|---------------------------------------------------------------------------------------------|
| Cache Git Password for easy pushing                        | https://help.github.com/articles/set-up-git/#next-steps-authenticating-with-github-from-git |
| Checkout local copies of pull requests from GitHub remotes | https://gist.github.com/gnarf/5406589                                                       |
| Checkout branch on a fork                                  | https://help.github.com/articles/configuring-a-remote-for-a-fork/                           |


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


Create a remote branch based on the current branch

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git push <remote-name> <branch-name>`  | None  | None       |


Delete a local branch

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git branch -d <branch-name>`  | None  | None       |


Delete a remote branch

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git push origin :<branch-name>`  | None  | None       |


Show all local branches and their tracking information

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git branch -vv`  | None  | None       |


Pull a remote branch

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git fetch && git checkout <branch-name>`  | None  | None       |


View the latest commits in the repo

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git log`  | None  | None       |
| `git log --stat`  | The _--stat_ parameter specifies that each commit should display the names of the files that were changed  | None       |
| `git log -p`  | The _-p_ parameter specifies that each commit should display the full diff  | None       |


Add files to the staging area

| Command          | Notes | Screenshot |
|------------------|-------|------------|
| `git add <filename with extension>`  | By specifying the specific filename, only that file will be added to the staging area  | None       |
| `git add -A`  | The _-A_ parameter specifies that all tracked files will be added to the staging area	  | None       |
| `git add "*.txt"`  | The wildcard(*) character specifies that any file matching anything before the file 
extension will be added to the staging area  | None       |



