# DevOps 2026 - Sensitive File Handling Practice

## Overview
This repository is created for **learning and practicing Git operations related to sensitive files**.  
It demonstrates how to safely manage secrets like API keys, how to remove them from Git history, and how to prevent accidental exposure in a public repository.

---

## Contents
- `.env` (practice file containing a fake API key)
- `.gitignore` (to prevent `.env` from being committed)
- Example commands for Git history cleanup and safe practices

---

## Learning Goals
1. Understand the risks of committing sensitive data to a repository.
2. Practice safely removing secrets from Git history.
3. Learn the use of `.gitignore` to prevent future leaks.
4. Gain hands-on experience with Git commands like `git filter-repo`, `git push --force`, and Git commit workflows.

---

## Steps Practiced in This Repo

### 1. Create a sensitive file
```bash
echo API_KEY=12345-SECRET-KEY > .env


**2. Add and commit file (simulated mistake)
git add .
git commit -m "Add .env file (for practice)"
git push origin main

3. Remove sensitive file from Git history
git filter-repo --path .env --invert-paths
git remote add origin <repo-url>
git push origin --force --all
git push origin --force --tags

4. Prevent future leaks with .gitignore
echo .env >> .gitignore
git add .gitignore
git commit -m "Ignore .env files"
git push origin main --force

Safety Notes:
Never commit real API keys or passwords to a public repository.
Always use .gitignore for sensitive files.echo API_KEY=12345-SECRET-KEY > .env
