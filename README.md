<!---
{
  "depends_on": ["https://github.com/STEMgraph/650920e2-edbe-4dc5-8a0c-96e7d76344e3"],
  "author": "Stephan Bökelmann",
  "first_used": "2025-04-12",
  "keywords": ["git", "remote", "github", "push", "clone"]
}
--->

# Git: Using GitHub as a Remote

## 1) Introduction

You've worked with local Git repositories, practiced with branches, merges, and stashing, and you've even hosted your own remote repository using SSH.

Now it’s time to take the next step: **using GitHub as your remote**.

GitHub is a hosted Git platform that provides you with public or private remote repositories, user management, issue tracking, and many more features. In this exercise, you’ll:

- Create a GitHub account and a repository on the web
- Clone it to your local machine
- Work on it just like any Git project
- Push your changes back to GitHub
- Clone your project on another machine or directory

Understanding this process will help you integrate into collaborative workflows and prepare you for contributing to open source or managing your own projects online.

## 2) Tasks

1. **Create a GitHub Account**

   - Go to [https://github.com](https://github.com) and register an account.
   - Confirm your email address.
   - Optional: Configure a personal avatar, bio, and SSH keys in your profile.

2. **Create a New Repository on GitHub**

   - Click on the **"+"** icon in the top-right corner and choose **"New repository"**.
   - Set a name (e.g., `github-test`).
   - Do **not** initialize it with a README or license.
   - Choose **public** or **private** depending on your preference.
   - Click **Create repository**.

   ⚠️ This is the GitHub equivalent of running `git init --bare` on your remote machine — you're creating a place for your code to live, without any working directory!

3. **Clone the Repository to Your Local Machine**

   On your **local machine**, open a terminal and run:
   ```bash
   git clone git@github.com:<your-username>/github-test.git
   cd github-test
   ```

   This creates a full local Git repository with `origin` set to your GitHub repo via SSH.

4. **Add a File and Commit**

   Create a file called `hello.md` and add some content:
   ```bash
   echo "# Hello GitHub" > hello.md
   git add hello.md
   git commit -m "Add hello.md"
   ```

5. **Push to GitHub**

   Push your changes to the `main` (or `master`) branch:
   ```bash
   git push origin main
   ```

   Now go to your repository on GitHub in the browser and verify that `hello.md` is visible.

6. **Clone the Repository Elsewhere**

   On a second machine, or in a new directory:
   ```bash
   git clone git@github.com:<your-username>/github-test.git github-test-copy
   cd github-test-copy
   ```

   Check that `hello.md` is already present:
   ```bash
   cat hello.md
   ```

## 3) Questions

- What is the difference between `git@github.com:...` and `https://github.com/...` when cloning?
- Why does GitHub not give you a working directory on their servers?
- What are the benefits of hosting a repository on GitHub compared to using your own remote machine?
- What happens if you try to push without committing?
- What do you see if you go to the *"Commits"* tab of your GitHub repo?

## 4) Advice

GitHub is a great entry point into the world of remote collaboration. But remember: Git is the same underneath. You’ve already done this with your own server — GitHub just adds convenience, issue tracking, and collaboration tools.

Using GitHub via SSH is secure and fast. If SSH access doesn’t work for you, you can also clone and push via HTTPS — GitHub supports both.

Later on, you might want to explore Pull Requests, Branch Protection Rules, Actions (CI/CD), and GitHub Pages — all built on the same Git foundation.
