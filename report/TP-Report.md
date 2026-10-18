# TP Report: Git and GitHub

## Cover page

- **Student name:** [Your full name]
- **Partner (if applicable):** [Partner name]
- **Class/Group:** [Class or group]
- **Module:** Git and GitHub
- **Instructor:** [Instructor name]
- **Date:** [Submission date]

## Objective

The objective of this practical work is to understand local version control with Git, synchronize a repository with GitHub, use branches and merges, follow the GitHub Flow, and publish a basic website using GitHub Pages.

## Environment

- Computer/OS: macOS [version]
- Git version: `[paste output of git --version]`
- GitHub repository: [paste repository URL]
- Published website: [paste Pages URL after deployment]

> **Screenshot guidance:** Insert a genuine screenshot after each practical section. In Terminal on macOS, use `Cmd + Shift + 4` to capture a selected area. Save screenshots in `screenshots/` and replace each placeholder below with a Markdown image such as `![Step 1](../screenshots/01-git-version.png)`.

# Part 1 — Git

## 1. Git Tutorial / Git HOME

**Purpose:** The Git home/tutorial page introduces the course topics and links to each lesson.

**Work:** Open the assigned W3Schools tutorial and review the Git sections.

**Screenshot:** `[Insert screenshot of the tutorial home page]`

## 2. Git Intro

**Explanation:** Git is a distributed version-control system. It records project history and lets developers compare, share, and restore versions.

**Key concepts:**
- Repository: project plus its version history.
- Commit: a saved snapshot of staged changes.
- Branch: an independent line of development.
- Merge: combining changes from branches.
- Remote: a repository hosted elsewhere, such as GitHub.

**Screenshot:** `[Insert screenshot of the introduction page]`

## 3. Git Get Started

Run these commands in Terminal:

```bash
mkdir git-github-tp
cd git-github-tp
git init
git status
```

`mkdir` creates a directory, `cd` enters it, `git init` initializes a local repository, and `git status` reports its state.

**Screenshot:** `[Insert screenshot showing git init and git status]`

> If you are using the provided project folder, do not create a second folder inside it. Open Terminal in the project folder and run `git init` there instead.

## 4. Git New Files

Create a file and inspect the repository:

```bash
echo "# Git and GitHub TP" > notes.md
ls
git status
```

A newly created file is initially **untracked**: Git can see it, but it is not yet included in version history.

**Screenshot:** `[Insert screenshot showing notes.md as untracked]`

## 5. Git Staging Environment

Stage a file, then check the status:

```bash
git add notes.md
git status
```

The staging area is the preparation area for the next commit. To unstage a file if needed:

```bash
git restore --staged notes.md
```

**Screenshot:** `[Insert screenshot showing a staged file]`

## 6. Git Commit

Save staged changes to the local history:

```bash
git add notes.md
git commit -m "Add initial notes"
git log --oneline
```

A commit records a snapshot and a message. Commits are local until pushed to a remote repository.

**Screenshot:** `[Insert screenshot showing successful commit and git log]`

## 7. Git Help

Git includes built-in help:

```bash
git help
git help status
git status -h
```

The help system documents commands and their available options.

**Screenshot:** `[Insert screenshot showing Git help output]`

## 8. Git Branch

List branches and create a feature branch:

```bash
git branch
git switch -c feature-demo
git branch
```

A branch lets you work on changes independently from the main line. `git switch -c` creates and switches to the new branch.

**Screenshot:** `[Insert screenshot showing feature-demo as the current branch]`

## 9. Git Branch Merge

Make a change on the feature branch, commit it, and merge it into `main`:

```bash
echo "Branch and merge practice" >> notes.md
git add notes.md
git commit -m "Add branch practice note"
git switch main
git merge feature-demo
git log --oneline --graph --all
```

This demonstrates a merge when the changes can be combined automatically. If Git reports conflicts, open the conflicted file, resolve the marked sections, then run `git add <file>` and `git commit` to finish the merge.

**Screenshot:** `[Insert screenshot showing merge result and graph]`

# Part 2 — GitHub

## 10. GitHub Get Started

1. Sign in at https://github.com/.
2. Create a repository named `git-github-tp`.
3. For the simplest first push, create it without adding a README, license, or `.gitignore` on GitHub.
4. Copy its HTTPS URL.

**Screenshot:** `[Insert screenshot of the GitHub repository page]`

## 11. GitHub Edit Code

On GitHub, open a file and use the pencil/Edit control if available. Make a small change, enter a descriptive commit message, and commit it on the default branch or a new branch.

This demonstrates editing files directly in the GitHub web interface.

**Screenshot:** `[Insert screenshot of the edit screen and resulting commit]`

## 12. Pull from GitHub

If you edited a file on GitHub, download the remote changes locally:

```bash
git pull origin main
git status
```

`git pull` fetches remote changes and integrates them into the current branch. Commit or stash conflicting local changes before pulling if Git requires it.

**Screenshot:** `[Insert screenshot showing git pull and status]`

## 13. Push to GitHub

For the local project, connect the remote and upload the branch:

```bash
git remote add origin https://github.com/YOUR-USERNAME/git-github-tp.git
git remote -v
git push -u origin main
```

Replace `YOUR-USERNAME` with your actual username. If `origin` already exists, inspect it with `git remote -v` instead of adding it again. The `-u` option sets the upstream so future pushes can usually use `git push`.

**Screenshot:** `[Insert screenshot showing successful push and files visible on GitHub]`

## 14. GitHub Branch

Create a branch on your local computer and push it to GitHub:

```bash
git switch -c feature-readme
echo "Feature branch experiment" >> notes.md
git add notes.md
git commit -m "Demonstrate a feature branch"
git push -u origin feature-readme
```

Refresh GitHub and verify that the new branch is listed.

**Screenshot:** `[Insert screenshot of the branch selector on GitHub]`

## 15. Pull Branch from GitHub

Fetch branch information and switch to a remote branch:

```bash
git fetch origin
git branch -a
git switch --track origin/feature-readme
```

If you already created a local branch with that name, use `git switch feature-readme` instead. This demonstrates retrieving a branch that exists on the remote.

**Screenshot:** `[Insert screenshot showing the remote branch and current branch]`

## 16. Push Branch to GitHub

After committing changes on the branch, publish them:

```bash
git switch feature-readme
git add .
git commit -m "Update feature branch"
git push
```

If this branch has no upstream yet, use `git push -u origin feature-readme`.

**Screenshot:** `[Insert screenshot showing the branch push]`

## 17. GitHub Flow

GitHub Flow is a lightweight collaboration workflow:

1. Create a descriptive branch.
2. Make a small change.
3. Commit and push the branch.
4. Open a Pull Request on GitHub.
5. Review the changes.
6. Merge the Pull Request.
7. Delete the branch if it is no longer needed.

**Practical demonstration:** Open a Pull Request from `feature-readme` into `main`, review the changed files, and merge it if the comparison is correct.

**Screenshot:** `[Insert screenshot of the Pull Request and merged status]`

## 18. GitHub Pages

This repository includes `index.html` and `style.css` for a simple static website.

1. Push both files to the `main` branch.
2. Open the repository's **Settings → Pages**.
3. Under the build/deployment source, select **Deploy from a branch**.
4. Select branch `main` and folder `/ (root)`, then save.
5. Wait for deployment and open the URL shown in the Pages settings.

The address normally follows this pattern:

`https://YOUR-USERNAME.github.io/git-github-tp/`

Use the exact URL GitHub displays if it differs.

**Screenshot:** `[Insert screenshot of Pages settings and the published website]`

# Conclusion

This practical work demonstrates the main Git workflow: create files, stage changes, commit snapshots, inspect history, create branches, and merge work. It also demonstrates GitHub collaboration through remote synchronization, branch publishing, Pull Requests, and GitHub Pages deployment.

## Final verification checklist

- [ ] Git version and user configuration checked
- [ ] Local repository initialized
- [ ] New file created and staged
- [ ] Commit created and history inspected
- [ ] Help command tested
- [ ] Branch created and merged
- [ ] GitHub repository created
- [ ] Local project pushed to GitHub
- [ ] Remote change pulled locally
- [ ] Feature branch pushed and retrieved
- [ ] Pull Request created and reviewed
- [ ] GitHub Pages website published
- [ ] Real screenshots added for each section
- [ ] Repository and website URLs added to the report
