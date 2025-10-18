# Draft Pull Request Workflow - Multi-System Development

## Overview
Work on the same feature across multiple systems using a single Draft PR, accumulating all commits before merging to main.

## Initial Setup (System 1)

### Step 1: Create Feature Branch
```bash
# Ensure you're on main branch
git checkout main
git pull origin main

# Create and switch to feature branch
git checkout -b feature/fitness-app-implementation
```

### Step 2: Make Initial Changes
```bash
# Make your code changes
# Add files, modify code, etc.

# Stage and commit changes
git add .
git commit -m "Initial implementation: React UI setup"
```

### Step 3: Push Branch and Create Draft PR
```bash
# Push branch to remote
git push origin feature/fitness-app-implementation
```

**On GitHub/GitLab:**
1. Go to your repository
2. Click "New Pull Request"
3. Select `feature/fitness-app-implementation` → `main`
4. **Important**: Mark as "Draft" (checkbox/dropdown)
5. Add title: "WIP: Fitness App Implementation"
6. Create Draft PR
7. **Copy the PR URL** - this is your shareable link

## Working from System 2

### Step 1: Clone/Fetch the Branch
```bash
# If repository not cloned yet
git clone <repository-url>
cd <repository-name>

# Fetch the feature branch
git fetch origin
git checkout feature/fitness-app-implementation
```

### Step 2: Make Changes and Commit
```bash
# Make your changes
# Edit files, add features, etc.

# Stage and commit
git add .
git commit -m "Add backend API integration"

# Push changes to same branch
git push origin feature/fitness-app-implementation
```

## Switching Back to System 1

### Step 1: Pull Latest Changes
```bash
# Switch to feature branch (if not already)
git checkout feature/fitness-app-implementation

# Pull changes made from System 2
git pull origin feature/fitness-app-implementation
```

### Step 2: Continue Development
```bash
# Make more changes
git add .
git commit -m "Add YouTube API integration"
git push origin feature/fitness-app-implementation
```

## Continuous Multi-System Workflow

### Before Starting Work (Any System)
```bash
git checkout feature/fitness-app-implementation
git pull origin feature/fitness-app-implementation
```

### After Making Changes (Any System)
```bash
git add .
git commit -m "Descriptive commit message"
git push origin feature/fitness-app-implementation
```

## Final Merge Process

### Step 1: Clean Up Commits (Optional)
```bash
# Interactive rebase to squash commits
git rebase -i HEAD~n  # where n = number of commits

# Or create a clean summary commit
git reset --soft HEAD~n
git commit -m "Implement complete fitness app with React UI and Express backend"
git push --force origin feature/fitness-app-implementation
```

### Step 2: Mark PR as Ready
**On GitHub/GitLab:**
1. Go to your Draft PR
2. Click "Ready for Review" or remove "Draft" status
3. Request review if needed

### Step 3: Merge to Main
**On GitHub/GitLab:**
1. Use "Squash and Merge" option
2. Edit final commit message
3. Merge to main
4. Delete feature branch

## Key Benefits

✅ **Single PR**: All work consolidated in one place  
✅ **Shareable Link**: PR URL works across all systems  
✅ **Draft Protection**: Cannot accidentally merge  
✅ **Clean History**: Final merge shows as single commit  
✅ **Collaboration**: Multiple developers can work on same PR  

## Commands Quick Reference

```bash
# Start new feature
git checkout main && git pull origin main
git checkout -b feature/new-feature
git push origin feature/new-feature

# Work from another system
git fetch origin && git checkout feature/new-feature
git pull origin feature/new-feature

# Daily workflow
git add . && git commit -m "message"
git push origin feature/new-feature

# Final cleanup
git rebase -i HEAD~n
git push --force origin feature/new-feature
```

## Troubleshooting

**Issue**: Branch doesn't exist on System 2  
**Solution**: `git fetch origin` then `git checkout feature/branch-name`

**Issue**: Merge conflicts  
**Solution**: `git pull origin feature/branch-name` and resolve conflicts

**Issue**: Need to sync before starting work  
**Solution**: Always run `git pull origin feature/branch-name` first

**Issue**: Want to clean commit history  
**Solution**: Use `git rebase -i HEAD~n` before final merge