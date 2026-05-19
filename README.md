# 🌍 Adventure Northern Escapes – Hugo Website

This repository contains the **Hugo source files** for the Adventure Northern Escapes website.  
The site is automatically built and deployed to **GitHub Pages** using **GitHub Actions** whenever changes are pushed to the `main` branch.

🔗 **Live site:** [https://adventure-northern-escapes.co.uk/](https://adventure-northern-escapes.co.uk/)

---

## 🏗️ Project Overview

Adventure Northern Escapes is a UK-based property investment and management company dedicated to transforming real estate into thriving homes and unforgettable escapes.  
This site is built with **[Hugo](https://gohugo.io)** — a fast, modern static site generator.

---

## 📁 Folder Structure

```
hugo-website/
│
├── archetypes/          # Default archetypes for new content
├── content/             # Markdown (.md) content files
├── layouts/             # Templates and partials for the site
├── static/              # Static assets (CSS, JS, images, favicon)
├── hugo.toml            # Hugo site configuration
└── .github/workflows/   # GitHub Actions for auto-deployment
```

---

## ⚙️ For Developers & Collaborators

If you clone this repository and want to **run, modify, or redeploy** the site, follow these steps carefully.

### 🪜 Step 1: Install Hugo

Make sure you have the **Extended version** of Hugo installed.

**macOS:**
```bash
brew install hugo
```

**Windows:**
```bash
choco install hugo-extended
```

**Verify installation:**
```bash
hugo version
```

---

### 🪜 Step 2: Clone the Repository

```bash
git clone https://github.com/AdventureNorthernEscapes/hugo-website.git
cd hugo-website
```

---

### 🪜 Step 3: Check Configuration

Open `hugo.toml` and make sure `baseURL` matches the production site URL.

For this repo:
```toml
baseURL = "https://adventure-northern-escapes.co.uk/"
relativeURLs = true
canonifyURLs = true
```

If you change the custom domain or deploy the site somewhere else, **update the `baseURL`** to match the public production URL.

---

### 🪜 Step 4: Run Locally

Run a local development server:
```bash
hugo server -D
```

Then open:
👉 **http://localhost:1313**

---

### 🪜 Step 5: Build for Production

When you’re ready to publish changes:
```bash
hugo --minify
```

The static site will be generated in the `/public` folder.

> ⚠️ Note: You don’t need to push `/public` manually — the GitHub Action handles deployment automatically.

---

## 🚀 Automatic Deployment (GitHub Actions)

This repo is configured with **GitHub Pages via GitHub Actions**.

### ✅ How It Works
- Every push to the **`main` branch** triggers an automatic build and deployment.
- The site is built with Hugo.
- The generated files are published to GitHub Pages.

### 🧩 Workflow File
The deployment workflow is located at:
```
.github/workflows/deploy.yml
```

You can also manually trigger a deploy:
1. Go to the **Actions** tab in GitHub.
2. Select **“Deploy Hugo site to GitHub Pages”**.
3. Click **Run workflow → main**.

---

### 🧰 Common Tasks

**To update content:**
- Add or edit files inside `/content/`.

**To update images or CSS:**
- Add files under `/static/`.

**To trigger deployment manually:**
```bash
git commit --allow-empty -m "ci: trigger deploy"
git push origin main
```

---

## ⚡ Troubleshooting

| Issue | Cause | Fix |
|-------|--------|-----|
| CSS or images not loading | Wrong `baseURL` | Ensure it matches the public production URL. |
| Build failed in Actions | Missing theme or incorrect version | Confirm theme folder or submodule exists, and Hugo version matches locally. |
| No auto-deploy | Wrong workflow path | Ensure file is `.github/workflows/deploy.yml` and Actions are enabled in Settings. |

---

## 📜 License

This project is owned and maintained by **Adventure Northern Escapes**.  
All rights reserved © 2025 Adventure Northern Escapes.
