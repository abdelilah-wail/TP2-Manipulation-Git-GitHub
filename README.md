# Git and GitHub TP — Step-by-Step Solution

**Student:** [Your full name]  
**Group/Class:** [Your group]  
**Module:** Git and GitHub  
**Reference tutorial:** https://www.w3schools.com/git/default.asp?remote=github

This repository contains a practical walkthrough of the assigned Git and GitHub topics, a small website for GitHub Pages, and a report outline. Replace the placeholders with your information and add your own screenshots as you complete each step.

## Repository contents

- `README.md` — project overview and command reference
- `index.html` — small website to publish with GitHub Pages
- `style.css` — styling for the website
- `report/TP-Report.md` — report template with all requested sections and screenshot slots
- `screenshots/` — place your screenshots here

## Before starting

On macOS, open Terminal and check Git:

```bash
git --version
```

If Git is not installed, run:

```bash
xcode-select --install
```

Configure your commit identity (replace the examples):

```bash
git config --global user.name "Your Full Name"
git config --global user.email "your-email@example.com"
git config --global --list
```

Use your GitHub-associated email if you want your commits linked to your GitHub profile. These settings identify commit authors; they do not authenticate you to GitHub.

## Recommended workflow

1. Create a **public** GitHub repository named `git-github-tp` (do not initialize it with a README if you plan to push this local project).
2. Download/unzip this project and open Terminal in the `git_github_tp_solution` folder.
3. Initialize Git, create the first commit, connect your GitHub repository, and push:

```bash
git init
git branch -M main
git add .
git status
git commit -m "Add initial Git and GitHub TP files"
git remote add origin https://github.com/YOUR-USERNAME/git-github-tp.git
git remote -v
git push -u origin main
```

Replace `YOUR-USERNAME` with your actual GitHub username. If you already created a repository with a README, either clone that repository first and copy these files into it, or follow Git's merge instructions if the histories differ. GitHub may ask you to authenticate through your browser or credential manager; do not put passwords or tokens in the remote URL.

4. Follow every section in `report/TP-Report.md` in order and capture your own screenshots.
5. Enable GitHub Pages: on GitHub, open **Settings → Pages**, select **Deploy from a branch**, choose `main` and `/ (root)`, then save. Wait for deployment. Your URL will normally be `https://YOUR-USERNAME.github.io/git-github-tp/`.
6. Commit and push your completed report and screenshots:

```bash
git add .
git status
git commit -m "Complete TP report and screenshots"
git push
```

## Important notes

- Run commands from inside the repository unless a section says otherwise.
- Use `git status` often to understand what Git sees.
- Do not claim that a step succeeded until you have performed it and verified the result.
- Screenshots must show your real output or GitHub page. The `screenshots/` directory is initially empty; add genuine screenshots as you work.
- Do not upload access tokens, passwords, private keys, or other secrets.
