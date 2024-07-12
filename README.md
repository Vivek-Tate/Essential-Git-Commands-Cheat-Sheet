# Essential Git Commands Cheat Sheet

A comprehensive guide covering essential Git commands and operations, including repository management, making changes, parallel development, syncing, configuration, and project management. Perfect for quick reference and detailed workflows.

## Installation

### Linux

#### Debian/Ubuntu
```sh
sudo apt-get update
sudo apt-get install git
```

#### Fedora
```sh
sudo dnf install git
```

#### Arch Linux
```sh
sudo pacman -S git
```

### Windows

#### Using Git for Windows Installer
1. Download the Git for Windows installer from [git-scm.com](https://git-scm.com/download/win).
2. Run the installer and follow the instructions.

#### Using Chocolatey
```sh
choco install git
```

### macOS

#### Using Homebrew
```sh
brew install git
```

#### Using MacPorts
```sh
sudo port install git
```

#### Using Xcode Kit (macOS)
- Git comes pre-installed with Xcode.

## Git Operations & Commands

### 1. Repository Setup

|   Operation   | Command                                      | Description                                   |
|:-------------:|----------------------------------------------|-----------------------------------------------|
| Init          | `git init`                                   | Create a new local git repository             |
| Clone         | `git clone [Repo URL]`                       | Create a copy of the original repository      |
| Fork          | `git fork`                                   | Create a copy of the original repository on GitHub |
| Remove Init   | `rm -rf .git`                                | Remove the `.git` directory                   |

### 2. Committing Changes

|   Operation   | Command                                      | Description                                   |
|:-------------:|----------------------------------------------|-----------------------------------------------|
| Status        | `git status`                                 | Check the status of the current repository    |
| Add           | `git add [file names]`                       | Add single or multiple files to the staging area |
|               | `git add .`                                  | Add all files to the staging area             |
| Commit        | `git commit -m "[message]"`                  | Commit the changes with a message             |
| Log           | `git log`                                    | Show details of all commits                   |
|               | `git log [Branch Name]`                      | Show details of specific commits              |
| Show          | `git show [Commit ID]`                       | Show detailed information of a specific commit |
| Reset         | `git reset`                                  | Reset the HEAD to the last commit and discard new changes |
|               | `git reset [file name]`                      | Remove specific files from the staging area   |
|               | `git reset --soft HEAD~1`                    | Undo the last commit but keep the changes staged |
|               | `git reset --hard HEAD~1`                    | Undo the last commit and discard the changes  |
| Stash         | `git stash`                                  | Stash changes into the staging area           |
|               | `git stash list`                             | Show all stash entries                        |
|               | `git stash apply`                            | Apply a stash                                 |
| Clean         | `git clean -f`                               | Remove untracked files from the working directory |
|               | `git clean -fd`                              | Remove untracked files and directories        |
| Alias         | `git config --global alias.[alias] [command]`| Shortened commands that map to longer commands|
| Tag           | `git tag [Tag Name]`                         | Add a tag at a specific point for extra information |
|               | `git tag -l`                                 | List all tags                                 |
|               | `git tag -a [Tag Name] -m "[Message]"`       | Create an annotated tag                       |
| Blame         | `git blame [File Name]`                      | Show the person who made changes in a file    |
| Diff          | `git diff [Branch Name]`                     | Compare the branch with the active branch     |
|               | `git diff [Primary Branch Name] [Secondary Branch Name]` | Compare two branches                    |
|               | `git diff [Primary Commit Name] [Secondary Commit Name]` | Compare two commits                    |
| Apply a Patch | `git apply [Patch File]`                     | Apply changes from a patch file               |
| Show Remote Branches | `git branch -r`                      | List remote branches                          |
| Check File History | `git log --follow [file name]`         | Show the commit history of a specific file, including renames |
| Amend Commit  | `git commit --amend`                         | Modify the last commit with new changes       |
| Check Ignore  | `git check-ignore -v [file name]`            | Check if a file is being ignored by .gitignore|

### 3. Branching and Merging

|   Operation   | Command                                      | Description                                   |
|:-------------:|----------------------------------------------|-----------------------------------------------|
| Branch        | `git branch`                                 | List all available branches                   |
|               | `git branch [New Branch Name]`               | Create a new branch from the active branch    |
|               | `git branch --delete/-d [Existing Branch Name]` | Delete a branch in the local repository    |
|               | `git branch -m [Existing Branch Name] [New Branch Name]` | Rename an existing branch               |
| Checkout      | `git checkout [Existing Branch Name/ New Branch Name]` | Checkout to another branch or create a new one |
| Merge         | `git merge [Secondary Branch Name]`          | Merge the secondary branch into the active branch |
| Rebase        | `git rebase [Branch Name]`                   | Update the active branch with commits from the secondary branch |
| Cherry Pick   | `git cherry-pick [Commit ID]`                | Apply the changes from a specific commit onto the current branch |
| Revert        | `git revert [Commit ID]`                     | Create a new commit that undoes the changes of a specific commit |
| Squash Commits| `git rebase -i [Commit ID/Branch Name]`      | Interactive rebase to squash commits          |
| List Commits between Two Branches | `git log [Branch 1]..[Branch 2]` | List commits that are in Branch 2 but not in Branch 1 |
| Bisect        | `git bisect start`                           | Start a bisect session                        |
|               | `git bisect bad`                             | Mark the current commit as bad                |
|               | `git bisect good [Commit ID]`                | Mark a known good commit                      |
| Rename Branch | `git branch -m [New Branch Name]`            | Rename the current branch                     |
| Restore Branch | `git checkout -b [Branch Name] [Commit ID]` | Restore a branch that has been deleted        |
| Delete Remote Branch | `git push origin --delete [Branch Name]` | Delete a branch on the remote repository  |

### 4. Remote Synchronization

|   Operation   | Command                                      | Description                                   |
|:-------------:|----------------------------------------------|-----------------------------------------------|
| Remote        | `git remote -v`                              | Verify the remote repository URL              |
|               | `git remote add origin [repo URL]`           | Link a remote repository to the local repository |
|               | `git remote add upstream [repo URL]`         | Add the upstream repository                   |
|               | `git remote rename origin [New Repo Name]`   | Rename the remote repository                  |
|               | `git remote remove/rm origin`                | Remove the remote repository                  |
| Push          | `git push (-f optional) origin [Branch Name]` | Push local changes to the remote repository (-f for force push) |
|               | `git push :[Old Branch Name] [New Branch Name]` | Rename the branch on the remote repository |
|               | `git push --delete origin [Branch Name]`      | Delete the remote branch                      |
| Pull          | `git pull origin [Branch Name]`              | Copy/update the remote repository to the local repository |
|               | `git pull --rebase origin [Branch Name]`     | Rebase the local commits on top of the upstream changes |
| Fetch         | `git fetch`                                  | Download objects and refs from another repository |
|               | `git fetch upstream`                         | Fetch changes from the upstream repository    |
| Submodule     | `git submodule add [Repo URL] [Path]`        | Add a submodule to the repository             |
|               | `git submodule update --init --recursive`    | Initialize, fetch, and checkout submodules    |

### 5. Git Configuration

|   Operation   | Command                                      | Description                                   |
|:-------------:|----------------------------------------------|-----------------------------------------------|
| Check Config  | `git config --list`                          | Check already configured parameters           |
| Global Config | `git config --global user.name "Vivek Shravan Tate"` | Configure username globally             |
|               | `git config --global user.email "vivektate.developer@gmail.com"` | Configure email globally               |
| Local Config  | `git config user.name "Vivek Shravan Tate"`  | Configure username locally                    |
|               | `git config user.email "vivektate.developer@gmail.com"` | Configure email locally                  |
| Configure SSH for GitHub | `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"` | Generate a new SSH key               |
|               | `ssh-add ~/.ssh/id_rsa`                      | Add SSH key to the ssh-agent                  |
| Alias Creation| `git config --global alias.[alias] [command]` | Create a shortcut for a Git command         |
| Edit Config   | `git config --global --edit`                 | Edit the global Git configuration file       |

### 6. Repository Management

|   Operation   | Command                                      | Description                                   |
|:-------------:|----------------------------------------------|-----------------------------------------------|
| Archive       | `git archive --format=zip --output [path] [Branch Name]` | Archive the branch into a zip file    |
| Bundle        | `git bundle create ../repo.bundler [Branch Name]` | Create a file of the branch             |

### 7. Troubleshooting

|   Operation   | Command                                      | Description                                   |
|:-------------:|----------------------------------------------|-----------------------------------------------|
| Reflog        | `git reflog`                                 | Show a log of all references (HEAD changes)   |
| FSCK          | `git fsck`                                   | Check the integrity of the repository         |
| GC            | `git gc`                                     | Cleanup unnecessary files and optimize the repository |
| Reflog Recovery | `git checkout -b [branch] [reflog commit]` | Recover a branch using a commit from reflog   |

### 8. Git Hooks

|   Operation   | Command                                      | Description                                   |
|:-------------:|----------------------------------------------|-----------------------------------------------|
| Create Hook   | `vi .git/hooks/[hook-name]`                  | Create or edit a Git hook                     |
| Enable Hook   | `chmod +x .git/hooks/[hook-name]`            | Make the hook script executable               |
| Sample Hook   | `cp .git/hooks/[hook-name].sample .git/hooks/[hook-name]` | Copy and edit a sample hook script   |

### Get in Touch

Please feel free to reach out if you have any issues or suggestions. Connect with me on [LinkedIn](https://www.linkedin.com/in/vivektate/) or email me at vivektate.developer@gmail.com.
