### **Comprehensive Git Commands Documentation**

This documentation provides a detailed guide to essential Git commands, organized by categories for better understanding.

## **1. Setting Up Git**

### **Installation**
- Install Git from [git-scm.com](https://git-scm.com).

### **Configuration**
```bash
git config --global user.name "Your Name"      # Set your name
git config --global user.email "your.email@example.com"  # Set your email
git config --global color.ui auto             # Enable color in Git output
git config --global core.editor "code --wait" # Set VSCode as default editor (or another editor)
```

Check configuration:
```bash
git config --list
```

---

## **2. Repository Basics**

### **Initialize Repository**
```bash
git init             # Initialize a new repository
git init [dir]       # Initialize repository in a specific directory
```

### **Clone Repository**
```bash
git clone [URL]      # Clone an existing repository
git clone [URL] [dir] # Clone into a specific directory
```

---

## **3. Tracking Changes**

### **Check Status**
```bash
git status           # Show working directory status
```

### **Add Changes**
```bash
git add [file]       # Stage a specific file
git add .            # Stage all changes in the current directory
```

### **Commit Changes**
```bash
git commit -m "message"  # Commit with a message
git commit              # Open editor for detailed commit message
```

### **Remove File**
```bash
git rm [file]        # Remove file from repository and working directory
git rm --cached [file]  # Remove file from repository only
```

---

## **4. Viewing History**

### **Log History**
```bash
git log              # Show commit history
git log --oneline    # Condensed view of commit history
git log --graph      # Display commit history as a graph
git log -p           # Show patches (changes) with each commit
```

### **Show Changes**
```bash
git diff             # Show unstaged changes
git diff --staged    # Show staged changes
```

---

## **5. Branching and Merging**

### **Branch Management**
```bash
git branch           # List branches
git branch [branch]  # Create a new branch
git branch -d [branch] # Delete a branch
git branch -D [branch] # Force delete a branch
```

### **Switch Branch**
```bash
git checkout [branch]       # Switch to a branch
git checkout -b [branch]    # Create and switch to a new branch
git switch [branch]         # Alternate for `checkout`
git switch -c [branch]      # Create and switch to a new branch
```

### **Merge Branches**
```bash
git merge [branch]    # Merge a branch into the current branch
```

---

## **6. Remote Repositories**

### **Connect to Remote**
```bash
git remote add origin [URL] # Add remote repository
git remote -v              # List remote connections
```

### **Push Changes**
```bash
git push                 # Push changes to remote
git push origin [branch] # Push specific branch
git push -u origin [branch] # Push and set upstream
```

### **Pull Changes**
```bash
git pull                 # Fetch and merge changes from remote
git pull origin [branch] # Pull specific branch
```

### **Fetch Changes**
```bash
git fetch                # Fetch changes from remote without merging
```

---

## **7. Undoing Changes**

### **Unstage Changes**
```bash
git reset [file]         # Unstage a file
git reset                # Unstage all changes
```

### **Discard Changes**
```bash
git checkout -- [file]   # Discard local changes to a file
```

### **Reset Commits**
```bash
git reset --soft HEAD~1  # Undo last commit, keep changes staged
git reset --mixed HEAD~1 # Undo last commit, unstage changes
git reset --hard HEAD~1  # Undo last commit, discard changes
```

---

## **8. Stashing**

### **Save Work**
```bash
git stash               # Save uncommitted changes
git stash save "message" # Save changes with a message
```

### **Apply Stash**
```bash
git stash apply         # Apply latest stash
git stash apply [stash@{n}] # Apply a specific stash
```

### **List Stashes**
```bash
git stash list
```

### **Drop Stash**
```bash
git stash drop [stash@{n}] # Remove a specific stash
git stash clear          # Remove all stashes
```

---

## **9. Tagging**

### **Create Tag**
```bash
git tag [tag_name]          # Create a tag
git tag -a [tag_name] -m "message" # Annotated tag
```

### **Push Tags**
```bash
git push origin [tag_name]  # Push a specific tag
git push origin --tags      # Push all tags
```

---

## **10. Advanced Commands**

### **Revert Commit**
```bash
git revert [commit_hash]    # Revert a specific commit
```

### **Cherry-Pick**
```bash
git cherry-pick [commit_hash] # Apply a specific commit to another branch
```

### **Squash Commits**
```bash
git rebase -i HEAD~n        # Squash last n commits interactively
```

---

## **11. Troubleshooting**

### **Remove Remote Branch**
```bash
git push origin --delete [branch]
```

### **Resolve Conflicts**
1. Edit conflicting files.
2. Mark conflicts as resolved:
   ```bash
   git add [file]
   ```
3. Commit changes:
   ```bash
   git commit
   ```

---

## **12. Useful Aliases**
```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.last 'log -1 HEAD'
```

---

## **13. Git Ignore**
Create a `.gitignore` file to exclude files:
```
# Ignore log files
*.log

# Ignore directories
/temp/
```

Add the `.gitignore` file to the repository:
```bash
git add .gitignore
git commit -m "Added .gitignore"
```

---

## **14. Git SSH Setup**
- Generate SSH key:
  ```bash
  ssh-keygen -t rsa -b 4096 -C "your.email@example.com"
  ```
- Add SSH key to your account ([GitHub guide](https://github.com/settings/keys)).

---