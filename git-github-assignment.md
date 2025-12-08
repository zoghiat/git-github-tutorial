# Git and GitHub Hands-On Assignment

## Overview

This assignment will help you practice all the essential Git and GitHub skills. You'll fork a repository, work with it locally, and collaborate using GitHub.

## Prerequisites

- Git installed on your computer
- GitHub account created
- Text editor installed

---

## Part 1: Initial Setup

### Task 1.1: Configure Git

Set up your Git identity on your local machine.

```
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### Task 1.2: Fork the Repository

1. Go to the provided repository URL(https://github.com/KianYari/git-github-tutorial)
2. Click the "Fork" button in the top-right corner
3. This creates a copy of the repository in your GitHub account

### Task 1.3: Clone Your Fork

Clone your forked repository to your local machine.

```
git clone https://github.com/YOUR-USERNAME/repository-name.git
cd repository-name
```

---

## Part 2: Basic Git Workflow

### Task 2.1: Create a New File

1. Create a file named `about-me.txt`
2. Add your name, favorite programming language, and why you're learning Git
3. Check the status of your repository

```
git status
```

### Task 2.2: Stage and Commit

1. Stage your new file
2. Commit it with a meaningful message

```
git add about-me.txt
git commit -m "Add personal introduction in about-me.txt"
```

### Task 2.3: View History

View your commit history.

```
git log
git log --oneline
```

---

## Part 3: Working with .gitignore

### Task 3.1: Create Files to Ignore

1. Create a file named `secrets.txt` with some dummy secret data
2. Create a file named `test.log`
3. Check the status - Git should show both as untracked

### Task 3.2: Create .gitignore

1. Create a `.gitignore` file
2. Add the following patterns:

```
secrets.txt
*.log
```

3. Check status again - the ignored files should no longer appear as untracked

### Task 3.3: Commit .gitignore

Stage and commit the `.gitignore` file.

```
git add .gitignore
git commit -m "Add .gitignore to exclude secrets and logs"
```

---

## Part 4: Branching

### Task 4.1: Create a New Branch

Create a branch called `feature/add-skills`.

```
git branch feature/add-skills
git checkout feature/add-skills
```

Or use the shortcut:

```
git checkout -b feature/add-skills
```

### Task 4.2: Work on the Branch

1. Create a new file called `skills.txt`
2. List 5 technical skills you have or want to learn
3. Stage and commit the file

```
git add skills.txt
git commit -m "Add skills list"
```

### Task 4.3: Switch Back to Main

Switch back to the main branch.

```
git checkout main
```

Note: `skills.txt` will not be visible in the main branch because it only exists in the feature branch.

---

## Part 5: Using Git Stash

### Task 5.1: Make Uncommitted Changes

1. Make sure you're on the `main` branch
2. Edit `about-me.txt` and add a new line about your goals
3. Don't commit the changes yet

### Task 5.2: Stash Your Changes

You need to switch branches but don't want to commit yet.

```
git stash
git status
```

### Task 5.3: Apply Stashed Changes

```
git stash list
git stash pop
```

Now commit the changes you just restored.

```
git add about-me.txt
git commit -m "Add goals to about-me.txt"
```

---

## Part 6: Undoing Changes

### Task 6.1: Make a Commit to Revert

1. Create a file called `mistake.txt` with some content
2. Stage and commit it

```
git add mistake.txt
git commit -m "Add mistake file"
```

### Task 6.2: Use Git Revert

Undo the commit using revert.

```
git revert HEAD
```

Note: This creates a new commit that undoes the previous commit. The file will be removed but the history is preserved.

### Task 6.3: Use Git Reset

1. Create another file called `test-reset.txt`
2. Stage and commit it
3. Use reset to undo the commit

```
git add test-reset.txt
git commit -m "Add test reset file"
git reset --soft HEAD~1
```

Note: With `--soft`, the commit is removed but changes remain staged. The file still exists but the commit is gone from history.

---

## Part 7: Removing Files from Git

### Task 7.1: Accidentally Track a File

1. Create a file called `password.txt`
2. Add and commit it (oops!)

```
git add password.txt
git commit -m "Add password file"
```

### Task 7.2: Remove from Git but Keep Locally

Remove the file from Git tracking but keep it on your computer.

```
git rm --cached password.txt
git add .gitignore
git commit -m "Remove password.txt from tracking and add to gitignore"
```

### Task 7.3: Add to .gitignore and Commit

1. Add `password.txt` to your `.gitignore` file
2. Commit both changes

```
git add .gitignore
git commit -m "Remove password.txt from tracking and add to gitignore"
```

---

## Part 8: Pushing to GitHub

### Task 8.1: Push Your Main Branch

Push all your main branch commits to GitHub.

```
git checkout main
git push -u origin main
```

### Task 8.2: Push Your Feature Branch

Push your feature branch to GitHub.

```
git checkout feature/add-skills
git push -u origin feature/add-skills
```

---

## Part 9: Working with Remote Changes

### Task 9.1: Make a Change on GitHub

1. Go to your repository on GitHub
2. Edit the `README.md` file directly on GitHub (use the edit button)
3. Add a new line and commit it through the web interface

### Task 9.2: Fetch Changes

See what changed without merging.

```
git fetch origin
git log origin/main
```

Note: Fetch downloads the changes but doesn't merge them yet.

### Task 9.3: Pull Changes

Now pull the changes to update your local branch.

```
git checkout main
git pull origin main
```

Verify that your local README.md now has the changes you made on GitHub.

---

## Part 10: Creating a Pull Request

### Task 10.1: Create Pull Request

1. Go to your forked repository on GitHub
2. Click "Pull requests" → "New pull request"
3. Set base repository to your fork, base branch to `main`
4. Set compare branch to `feature/add-skills`
5. Click "Create pull request"
6. Add a title: "Add skills list to repository"
7. Add a description explaining what you added
8. Create the pull request

### Task 10.2: Merge Pull Request

1. Review your own pull request
2. Click "Merge pull request"
3. Confirm the merge
4. Delete the branch on GitHub (optional)

### Task 10.3: Update Local Repository

Pull the merged changes to your local main branch.

```
git checkout main
git pull origin main
```

Verify that `skills.txt` is now in your main branch locally.

---

## Part 11: Git Diff

### Task 11.1: Make Changes and View Diff

1. Edit `about-me.txt` and add more information
2. Before committing, view the changes

```
git diff
```

3. Commit the changes

```
git add about-me.txt
git commit -m "Update about-me with additional information"
```

### Task 11.2: View Diff Between Commits

```
git log --oneline
git diff COMMIT1 COMMIT2
```

(Replace COMMIT1 and COMMIT2 with actual commit hashes from your log)

This shows the differences between two specific commits in your history.

---

## Part 12: Final Reflection

### Task 12.1: Create Summary Document

Create a file called `learning-summary.md` with the following sections:

1. **Commands I learned**: List all Git commands you used
2. **Challenges faced**: What was difficult?
3. **Key takeaways**: What are the 3 most important things you learned?
4. **Questions**: Any remaining questions about Git/GitHub?

### Task 12.2: Final Push

Commit and push your summary.

```
git add learning-summary.md
git commit -m "Add learning summary and reflections"
git push origin main
```

### Task 12.3: Final Verification

Verify all your work is on GitHub:

1. Go to your forked repository on GitHub
2. Check that all your commits are visible
3. Check that all required files are present:
   - `about-me.txt`
   - `skills.txt`
   - `.gitignore`
   - `learning-summary.md`
   - Updated `README.md`
4. Verify that your pull request was merged

---

## Submission Requirements

Submit the following:

1. Link to your forked GitHub repository
2. Ensure all commits have been pushed to GitHub
3. Ensure your `learning-summary.md` file is in the repository

---

## Tips for Success

- Read each instruction carefully
- If you make a mistake, that's okay! Document it in your learning summary
- Use `git status` frequently to understand what's happening
- Use `git log` to verify your commits were created
- Push your changes regularly to ensure they're on GitHub
- Ask for help if you get stuck

## Resources

- [Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- Your course syllabus

Good luck! Remember, the goal is to learn, so take your time and experiment!
