# 🚀 Project 1: Static Portfolio Website with CI/CD

**Author:** Min Raj Panday
**Goal:** Deploy a simple static portfolio site to GitHub Pages automatically using GitHub Actions.

## 🌟 Key DevOps Concepts Demonstrated

* **Continuous Deployment (CD):** Any change merged to the `main` branch is automatically deployed to the live website.
* **Infrastructure as Code (IaC) for CI/CD:** The entire deployment pipeline is defined in the declarative YAML file (`.github/workflows/deploy.yml`).
* **GitHub Actions:** Utilizing a managed service for robust, serverless automation.

## ⚙️ CI/CD Workflow Breakdown

The deployment pipeline is triggered on every `push` to the `main` branch:

1.  **Trigger:** `on: push: branches: [main]` starts the workflow.
2.  **Checkout:** `actions/checkout@v4` pulls the latest code.
3.  **Deployment:** `peaceiris/actions-gh-pages@v3` is used to push the contents of the root directory (`publish_dir: ./`) to a special branch called `gh-pages`.
4.  **GitHub Pages Hook:** GitHub Pages is configured to serve the website content from the `gh-pages` branch.

## 🚀 Setup & Deployment Guide

### Prerequisites
1.  A GitHub Account.
2.  Basic knowledge of Git commands.

### Steps
1.  **Initialize Git:**
    ```bash
    git init
    git add .
    git commit -m "Initial commit of static site and CI/CD workflow"
    ```
2.  **Create Repository:** Create a new remote repository on GitHub and push your local code to the `main` branch.
    ```bash
    git remote add origin <YOUR_REPO_URL>
    git branch -M main
    git push -u origin main
    ```
3.  **Configure GitHub Pages:**
    * Go to your GitHub repository **Settings**.
    * Navigate to **Pages** on the left sidebar.
    * Under "Build and deployment," set the **Source** to **Deploy from a branch**.
    * Set the **Branch** to **`gh-pages`** and the folder to **`/ (root)`**.
    * Click **Save**.

The first push will automatically trigger the GitHub Action, which will create the `gh-pages` branch. Once the action is complete (check the **Actions** tab!), the deployment URL will be available under **Settings > Pages**.

**Future deployments only require pushing to the `main` branch!**