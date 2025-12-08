# Git and GitHub Curriculum

## 1. Introduction to Version Control

- What is version control and why use it?
- Benefits of tracking changes
- Overview of Git vs GitHub

## 2. Getting Started with Git

- Installing Git
- Basic Git configuration (username and email)

  ```
  git config --global user.name "Your Name"
  git config --global user.email "your.email@example.com"
  ```

- Setting up a text editor for Git

## 3. Creating Your First Repository

- Initializing a repository
  ```
  git init
  ```
- Understanding the `.git` folder
- The working directory concept

## 4. Basic Git Workflow

- Checking repository status
  ```
  git status
  ```
- Staging files
  ```
  git add filename.txt
  git add .
  ```
- Unstaging files (removing from Git tracking)
  ```
  git rm --cached filename.txt
  ```
- Saving changes
  ```
  git commit -m "Your commit message"
  ```
- Writing good commit messages
- The staging area concept
- Ignoring files with `.gitignore`
  ```
  # Create .gitignore file
  # Common patterns:
  *.log
  node_modules/
  .env
  ```
- When to use `.gitignore` vs `git rm --cached`

## 5. Viewing History

- Viewing commit history
  ```
  git log
  ```
- Simplified history view
  ```
  git log --oneline
  ```
- Viewing specific commits
  ```
  git show
  ```
- Viewing changes
  ```
  git diff
  ```

## 6. Undoing Changes and Saving Work

- Temporarily saving changes
  ```
  git stash
  git stash list
  git stash pop
  git stash apply
  ```
- Undoing commits with revert (creates new commit)
  ```
  git revert commit-hash
  ```
- Undoing commits with reset (removes commits)
  ```
  git reset --soft HEAD~1   # Keep changes staged
  git reset --mixed HEAD~1  # Keep changes unstaged (default)
  git reset --hard HEAD~1   # Discard changes completely
  ```
- When to use stash vs commit
- Understanding revert vs reset:
  - **revert**: Creates a new commit that undoes changes (safe, preserves history)
  - **reset**: Moves branch pointer back, rewriting history (use carefully)

## 7. Working with Branches

- What are branches and why use them?
- Listing and creating branches
  ```
  git branch
  git branch new-branch-name          # create branch
  git checkout -b new-branch-name     # create and switch
  ```
- Switching between branches
  ```
  git checkout branch-name
  ```
- Basic branch workflows

## 8. Introduction to GitHub

- What is GitHub?
- Creating a GitHub account
- Understanding remote repositories
- GitHub interface overview
- Important: Main vs Master branch naming
  - Git creates a `master` branch by default
  - GitHub creates a `main` branch by default
  - This is just a naming difference (both work the same way)
  - You may need to rename your local branch to match GitHub

## 9. Connecting Local and Remote Repositories

- Linking to GitHub
  ```
  git remote add origin https://github.com/username/repository.git
  ```
- Sending changes to GitHub
  ```
  git push -u origin main
  git push
  ```
- Fetching changes from GitHub (without merging)
  ```
  git fetch
  git fetch origin
  ```
- Getting changes from GitHub (fetch + merge)
  ```
  git pull
  ```
- Understanding origin and main/master:
  - **origin**: The default name for your remote repository
  - **main vs master**: Default branch naming differences
    - Git (local): Uses `master` as default branch name
    - GitHub (remote): Uses `main` as default branch name (changed in 2020)
    - You can rename your branch to match:
      ```
      git branch -M main
      ```
    - Both names work the same way - it's just a naming convention
- Understanding fetch vs pull:
  - **fetch**: Downloads changes but doesn't merge them (safe to check what's new)
  - **pull**: Downloads and automatically merges changes (fetch + merge)

## 10. Cloning Repositories

- Copying repositories from GitHub
  ```
  git clone https://github.com/username/repository.git
  ```
- When and why to clone
- Working with cloned repositories

## 11. Basic Collaboration

- Forking repositories
- Creating pull requests
- Reviewing code on GitHub
- Basic contribution workflow

## 12. Essential Commands Review

```
git init
git add
git rm --cached
git commit
git status
git log
git stash
git revert
git reset
git branch
git checkout / git switch
git clone
git push
git fetch
git pull
```

## 13. Best Practices

- Commit often with clear messages
- Keep commits focused and atomic
- Pull before you push
- Use meaningful branch names
