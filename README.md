
# Dynamic Language Task

A comprehensive guide for working with Git and version control best practices.

## 📋 Table of Contents

- [About](#about)
- [Prerequisites](#prerequisites)
- [Git Setup](#git-setup)
- [Git Commands Reference](#git-commands-reference)
  - [Basic Configuration](#basic-configuration)
  - [Repository Operations](#repository-operations)
  - [Working with Changes](#working-with-changes)
  - [Branching and Merging](#branching-and-merging)
  - [Remote Operations](#remote-operations)
  - [History and Inspection](#history-and-inspection)
  - [Advanced Commands](#advanced-commands)
  - [Troubleshooting](#troubleshooting)
- [Common Workflows](#common-workflows)
- [Best Practices](#best-practices)
- [Contributing](#contributing)
- [License](#license)

## 📖 About

This repository provides a comprehensive reference for Git commands and version control workflows. Whether you're a beginner or an experienced developer, you'll find useful commands and best practices to streamline your development process.

## ✅ Prerequisites

Before you begin, ensure you have the following installed:

- **Git**: Version 2.0 or higher
  - Download from [git-scm.com](https://git-scm.com/)
  - Verify installation: `git --version`

## 🔧 Git Setup

### Initial Configuration

```bash
# Set your username
git config --global user.name "Your Name"

# Set your email
git config --global user.email "your.email@example.com"

# Set default branch name to 'main'
git config --global init.defaultBranch main

# Enable colorful output
git config --global color.ui auto

# Set default editor (examples)
git config --global core.editor "code --wait"  # VS Code
git config --global core.editor "vim"          # Vim
git config --global core.editor "nano"         # Nano

# View all configurations
git config --list
```

## 📚 Git Commands Reference

### Basic Configuration

| Command | Description |
|---------|-------------|
| `git config --global user.name "Name"` | Set your username globally |
| `git config --global user.email "email@example.com"` | Set your email globally |
| `git config --list` | List all Git configurations |
| `git config --global --edit` | Edit global configuration file |
| `git config --local user.name "Name"` | Set username for current repository only |

### Repository Operations

| Command | Description |
|---------|-------------|
| `git init` | Initialize a new Git repository |
| `git clone <url>` | Clone a repository from a remote source |
| `git clone <url> <directory>` | Clone repository into a specific directory |
| `git clone --depth 1 <url>` | Shallow clone (only latest commit) |
| `git remote -v` | List all remote repositories |
| `git remote add <name> <url>` | Add a new remote repository |
| `git remote remove <name>` | Remove a remote repository |
| `git remote rename <old> <new>` | Rename a remote repository |

### Working with Changes

| Command | Description |
|---------|-------------|
| `git status` | Show the working tree status |
| `git status -s` | Show status in short format |
| `git add <file>` | Add file to staging area |
| `git add .` | Add all changes to staging area |
| `git add -p` | Interactively stage changes |
| `git commit -m "message"` | Commit staged changes with a message |
| `git commit -am "message"` | Add and commit tracked files in one step |
| `git commit --amend` | Modify the last commit |
| `git commit --amend --no-edit` | Add changes to last commit without editing message |
| `git diff` | Show unstaged changes |
| `git diff --staged` | Show staged changes |
| `git diff <commit1> <commit2>` | Compare two commits |
| `git restore <file>` | Discard changes in working directory |
| `git restore --staged <file>` | Unstage a file |
| `git rm <file>` | Remove file from working tree and index |
| `git mv <old> <new>` | Move or rename a file |

### Branching and Merging

| Command | Description |
|---------|-------------|
| `git branch` | List all local branches |
| `git branch -a` | List all branches (local and remote) |
| `git branch <branch-name>` | Create a new branch |
| `git branch -d <branch-name>` | Delete a branch (safe) |
| `git branch -D <branch-name>` | Force delete a branch |
| `git branch -m <old> <new>` | Rename a branch |
| `git checkout <branch-name>` | Switch to a branch |
| `git checkout -b <branch-name>` | Create and switch to a new branch |
| `git switch <branch-name>` | Switch to a branch (modern alternative) |
| `git switch -c <branch-name>` | Create and switch to a new branch |
| `git merge <branch-name>` | Merge a branch into current branch |
| `git merge --no-ff <branch-name>` | Merge with a merge commit |
| `git merge --squash <branch-name>` | Merge and squash all commits |
| `git rebase <branch-name>` | Rebase current branch onto another branch |
| `git rebase -i <commit>` | Interactive rebase |
| `git cherry-pick <commit>` | Apply a specific commit to current branch |

### Remote Operations

| Command | Description |
|---------|-------------|
| `git fetch` | Download objects and refs from remote |
| `git fetch --all` | Fetch from all remotes |
| `git fetch --prune` | Remove references to deleted remote branches |
| `git pull` | Fetch and merge changes from remote |
| `git pull --rebase` | Fetch and rebase changes from remote |
| `git push` | Push commits to remote repository |
| `git push origin <branch-name>` | Push specific branch to remote |
| `git push -u origin <branch-name>` | Push and set upstream branch |
| `git push --force` | Force push (use with caution!) |
| `git push --force-with-lease` | Safer force push |
| `git push --tags` | Push all tags to remote |
| `git push --delete origin <branch>` | Delete remote branch |

### History and Inspection

| Command | Description |
|---------|-------------|
| `git log` | Show commit history |
| `git log --oneline` | Show compact commit history |
| `git log --graph` | Show branch graph |
| `git log --all --graph --oneline` | Show complete branch graph |
| `git log -n <number>` | Show last n commits |
| `git log --author="name"` | Show commits by specific author |
| `git log --since="2 weeks ago"` | Show commits from specific time |
| `git log --follow <file>` | Show history of a file |
| `git log -p <file>` | Show changes to a file over time |
| `git show <commit>` | Show details of a specific commit |
| `git show <commit>:<file>` | Show file content at specific commit |
| `git blame <file>` | Show who changed each line of a file |
| `git reflog` | Show reference logs (useful for recovery) |

### Advanced Commands

| Command | Description |
|---------|-------------|
| `git stash` | Stash current changes |
| `git stash save "message"` | Stash with a description |
| `git stash list` | List all stashes |
| `git stash pop` | Apply and remove latest stash |
| `git stash apply` | Apply latest stash without removing |
| `git stash drop` | Delete latest stash |
| `git stash clear` | Delete all stashes |
| `git clean -n` | Preview untracked files to be removed |
| `git clean -fd` | Remove untracked files and directories |
| `git tag <tag-name>` | Create a lightweight tag |
| `git tag -a <tag-name> -m "message"` | Create an annotated tag |
| `git tag -d <tag-name>` | Delete a local tag |
| `git tag -l "v1.*"` | List tags matching pattern |
| `git reset <commit>` | Reset to a commit (keep changes) |
| `git reset --soft <commit>` | Reset to commit (keep staged) |
| `git reset --hard <commit>` | Reset to commit (discard all changes) |
| `git reset --hard HEAD~1` | Undo last commit and changes |
| `git revert <commit>` | Create new commit that undoes changes |
| `git bisect start` | Start binary search for bug |
| `git worktree add <path> <branch>` | Create a linked working tree |

### Troubleshooting

| Command | Description |
|---------|-------------|
| `git status` | Check current state |
| `git log --oneline -10` | View recent commits |
| `git reflog` | View all reference changes (great for recovery) |
| `git fsck` | Check integrity of Git database |
| `git gc` | Cleanup unnecessary files and optimize |
| `git reset HEAD~1` | Undo last commit (keep changes) |
| `git checkout -- <file>` | Discard changes to a file |
| `git merge --abort` | Abort a merge in progress |
| `git rebase --abort` | Abort a rebase in progress |
| `git cherry-pick --abort` | Abort a cherry-pick in progress |
| `git fetch --prune` | Clean up deleted remote branches |

## 🔄 Common Workflows

### Starting a New Feature

```bash
# Update your local main branch
git checkout main
git pull origin main

# Create and switch to a feature branch
git checkout -b feature/new-feature

# Make changes and commit
git add .
git commit -m "Add new feature"

# Push to remote
git push -u origin feature/new-feature
```

### Keeping Your Branch Up to Date

```bash
# Fetch latest changes
git fetch origin

# Rebase your branch on main
git checkout feature/new-feature
git rebase origin/main

# Or merge main into your branch
git merge origin/main
```

### Fixing a Mistake in Last Commit

```bash
# Modify files
# Add changes to staging
git add <modified-files>

# Amend the last commit
git commit --amend --no-edit

# Force push (if already pushed)
git push --force-with-lease
```

### Undoing Changes

```bash
# Discard unstaged changes to a file
git restore <file>

# Unstage a file
git restore --staged <file>

# Undo last commit (keep changes)
git reset HEAD~1

# Undo last commit (discard changes)
git reset --hard HEAD~1

# Revert a commit (safe for shared branches)
git revert <commit-hash>
```

### Working with Stash

```bash
# Stash current changes
git stash save "Work in progress on feature X"

# List all stashes
git stash list

# Apply most recent stash
git stash pop

# Apply specific stash
git stash apply stash@{2}

# Delete a stash
git stash drop stash@{0}
```

### Resolving Merge Conflicts

```bash
# Start the merge
git merge feature-branch

# If conflicts occur, Git will notify you
# Edit conflicted files manually

# After resolving conflicts
git add <resolved-files>
git commit -m "Resolve merge conflicts"

# Or abort the merge
git merge --abort
```

## 💡 Best Practices

### Commit Messages

- **Use clear, descriptive messages**: `Add user authentication feature` not `Update files`
- **Use imperative mood**: `Add feature` not `Added feature`
- **Keep first line under 50 characters**
- **Add detailed description after blank line if needed**

Example:
```
Add user authentication feature

- Implement login and logout functionality
- Add JWT token validation
- Create user session management
```

### Branching Strategy

- **main/master**: Production-ready code
- **develop**: Integration branch for features
- **feature/***: New features (`feature/user-auth`)
- **bugfix/***: Bug fixes (`bugfix/login-error`)
- **hotfix/***: Urgent production fixes (`hotfix/security-patch`)

### General Tips

- ✅ Commit often with meaningful messages
- ✅ Pull before you push
- ✅ Use branches for new features
- ✅ Review changes before committing (`git diff`)
- ✅ Keep commits focused and atomic
- ✅ Write clear commit messages
- ❌ Don't commit sensitive data (passwords, API keys)
- ❌ Don't force push to shared branches
- ❌ Don't commit large binary files
- ❌ Don't commit generated files (use .gitignore)

### .gitignore Best Practices

Create a `.gitignore` file to exclude:

```gitignore
# Dependencies
node_modules/
vendor/

# Build outputs
dist/
build/
*.exe
*.dll

# Environment files
.env
.env.local

# IDE files
.vscode/
.idea/
*.swp

# OS files
.DS_Store
Thumbs.db

# Logs
*.log
logs/
```

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit your changes (`git commit -am 'Add improvement'`)
4. Push to the branch (`git push origin feature/improvement`)
5. Open a Pull Request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 📞 Additional Resources

- [Official Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [Atlassian Git Tutorials](https://www.atlassian.com/git/tutorials)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)

---

**Happy Coding! 🚀**
