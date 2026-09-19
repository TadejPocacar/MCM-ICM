# MCM-ICM

A repository for MCM/ICM modeling practice and competition preparation.

## Project Structure

- `code/` - MATLAB/Python code
- `data/` - Datasets
- `models/` - Mathematical models and notes
- `paper/` - Papers and reports
- `figures/` - Generated figures

---

## Git Workflow

The `main` branch is protected.

**Do not develop directly on `main`.**

All changes should be made on a separate branch and merged into `main` through a Pull Request.

Basic workflow:

```text
Update main
    ↓
Create branch
    ↓
Work
    ↓
Commit
    ↓
Push
    ↓
Pull Request
    ↓
Review
    ↓
Merge
    ↓
Update main
```

---

## 1. Update `main`

Before starting a new task:

```bash
git switch main
git pull --ff-only
```

This ensures that your local `main` is up to date with GitHub.

---

## 2. Create a Branch

Create a new branch for each task:

```bash
git switch -c feature/task-name
```

Examples:

```bash
git switch -c feature/matlab-basics
git switch -c feature/data-analysis
git switch -c feature/regression-model
git switch -c docs/update-paper
git switch -c fix/plot-error
```

Recommended prefixes:

| Prefix | Usage |
|---|---|
| `feature/` | New models, code or features |
| `fix/` | Bug fixes |
| `docs/` | README, documentation or paper |
| `data/` | Data processing |

One task should normally use one branch.

---

## 3. Make Changes

Edit files normally.

Check the current state:

```bash
git status
```

---

## 4. Add Changes

Add changed files to the staging area:

```bash
git add .
```

Check again if necessary:

```bash
git status
```

---

## 5. Commit

Create a commit:

```bash
git commit -m "message"
```

Examples:

```bash
git commit -m "feat: add regression model"
git commit -m "feat: add MATLAB visualization"
git commit -m "fix: correct calculation error"
git commit -m "docs: update README"
git commit -m "data: add cleaned dataset"
```

The commit message should briefly describe what was changed.

---

## 6. Push

For the first push of a new branch:

```bash
git push -u origin feature/task-name
```

Example:

```bash
git push -u origin feature/regression-model
```

After the first push, later updates only need:

```bash
git push
```

---

## 7. Create a Pull Request

After pushing your branch:

1. Open this repository on GitHub.
2. Go to **Pull requests**.
3. Click **New pull request**.
4. Select:

```text
base: main
compare: your-branch
```

5. Write a clear title and description.
6. Create the Pull Request.

Example:

```text
feature/regression-model
          ↓
     Pull Request
          ↓
         main
```

---

## 8. Review

At least **one teammate must approve the Pull Request** before it can be merged.

If new commits are pushed after approval, the previous approval becomes invalid and the Pull Request must be reviewed again.

Do not approve your own changes as a substitute for teammate review.

---

## 9. Merge

After review, merge the Pull Request into `main`.

Two merge methods are allowed:

### Merge

Keeps the complete commit history of the branch.

Use this when the individual commits are meaningful.

### Squash

Combines all commits in the Pull Request into one commit on `main`.

Use this when the branch contains many small commits such as:

```text
fix typo
test
fix plot
change parameter
fix bug
```

The final code is preserved; only the commit history is combined.

---

## 10. Start the Next Task

After the Pull Request has been merged:

```bash
git switch main
git pull --ff-only
```

Then create a new branch:

```bash
git switch -c feature/new-task
```

Do not continue using an old merged branch for a new task.

---

## Main Branch Protection

The `main` branch is protected by GitHub Rulesets.

Current rules:

- Changes must go through a Pull Request
- At least **1 approval** is required
- New commits invalidate previous approvals
- Force pushes are blocked
- Deleting `main` is restricted

Therefore, normal development should happen on branches rather than directly on `main`.

---

## Useful Git Commands

### Check repository status

```bash
git status
```

### Check branches

```bash
git branch
```

### Switch branch

```bash
git switch branch-name
```

### Create and switch to a new branch

```bash
git switch -c branch-name
```

### Update `main`

```bash
git switch main
git pull --ff-only
```

### View commit history

```bash
git log --oneline
```

### Add all changes

```bash
git add .
```

### Commit

```bash
git commit -m "message"
```

### Push

```bash
git push
```

---

## Team Rule

For every new task:

```text
main
 │
 │  git pull --ff-only
 │
 ├── feature/task
 │       │
 │       ├── edit files
 │       ├── git add .
 │       ├── git commit
 │       └── git push
 │
 │             ↓
 │        Pull Request
 │             ↓
 │           Review
 │             ↓
 │           Merge
 │             ↓
 └─────────── main
```

**Do not work directly on `main`.  
One task, one branch, one Pull Request.**