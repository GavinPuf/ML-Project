# GitHub for Beginners (Our Team Workflow)

This guide assumes you have **never used GitHub**. It explains how we use GitHub to collaborate on this ML project.

## Key idea
- `main` is the stable branch. It should always work.
- You do your work in a **feature branch** off of `main`.
- You share your changes via a **Pull Request (PR)** and get a teammate to review before merging.

## One‑time setup
1. **Install Git**:
   - macOS: install Xcode Command Line Tools (`xcode-select --install`) or use Homebrew (`brew install git`).
   - Windows: install [Git for Windows](https://gitforwindows.org/) and enable the "Git Bash" terminal.
2. **Create a GitHub account** and accept the invite to this repository.
3. **Set your identity** in Git (once):
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "you@example.com"
   ```

## The basic loop (do this for every task)
### A) Get the latest `main`
From your local repo:
```bash
# switch to main branch
git checkout main
# pull the latest changes from GitHub
git pull origin main
```

### B) Create a branch
Name your branch based on the work you are doing:
```bash
# e.g. adding data cleaning code
git checkout -b feature/your-short-task
```

### C) Make changes
Edit code, notebooks, or docs locally. Run code to make sure it works.

### D) Stage and commit
Use clear commit messages to describe what you did:
```bash
git add path/to/changed/files
# commit with a message summarising your changes
git commit -m "Add data cleaning script"
```

### E) Push your branch
Send your branch to GitHub:
```bash
git push -u origin feature/your-short-task
```
After the first push, subsequent pushes can use `git push`.

### F) Open a Pull Request (PR)
1. Go to the repository on GitHub.
2. Click **Pull requests** → **New pull request**.
3. Select your branch as the "compare" branch and `main` as the base.
4. Add a descriptive title and description. Mention what you changed and why.
5. Assign a teammate as the reviewer. They will read your code and give feedback.

PRs allow us to review and discuss changes before merging. See GitHub’s flow guide for more details.

### G) Address review comments
If your reviewer requests changes:
- Make the edits locally.
- Stage and commit them (`git add`, `git commit`).
- Push again (`git push`). Your PR will update automatically.
- When the reviewer is satisfied, they will approve the PR.

### H) Merge and delete your branch
Once approved:
1. Click **Merge pull request** on GitHub.
2. Choose **Delete branch** to remove your feature branch from GitHub (the history remains in the repository).

## Common problems
### I committed to the wrong branch
If you accidentally committed on `main` instead of a feature branch **and haven’t pushed**, you can fix it:
```bash
# create a new branch from your current state
git checkout -b feature/fix-main-commit
# reset main to the last good state
git checkout main
git reset --hard origin/main
```
Ask for help if you are unsure.

### Merge conflicts
Conflicts occur when two branches change the same lines. To resolve:
1. Checkout your branch and update with main: `git pull origin main`.
2. Git will mark conflicting files. Open them and edit the conflicting sections between `<<<<<<<` and `>>>>>>>` markers.
3. After resolving, stage the files and commit.

If you get stuck, ask a teammate for help.

## Golden rules for this repo
- **Do not commit data files** or large datasets; keep them in `data/` locally.
- **Never commit API keys or secrets**. Store them in a `.env` file and add it to `.gitignore`.
- **Keep each PR focused** on one task. Small, clear changes are easier to review.
- **One notebook per person** unless coordinating changes; do not overwrite another teammate's notebook.
