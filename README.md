# 📚 JTM020-Docs

> Technical documentation site built with **Astro** + **Fuwari** template, managed via **Obsidian** + **VaultCMS**.

[![Deploy to GitHub Pages](https://github.com/snap-star/JTM020-Docs/actions/workflows/deploy.yml/badge.svg)](https://github.com/snap-star/JTM020-Docs/actions/workflows/deploy.yml)

**Live site:** https://snap-star.github.io/JTM020-Docs/

---

## ✨ Features

- ⚡ **Astro** static site with Fuwari theme (Tailwind CSS + Svelte)
- 🌙 Light / Dark mode toggle
- 🔍 Full-text search via [Pagefind](https://pagefind.app/)
- 📋 Table of Contents on every doc page
- 📝 **Obsidian** as a local CMS via **VaultCMS**
- 🚀 Auto-deploy to GitHub Pages on every push to `main`
- 📦 RSS feed + sitemap included

---

## 🚀 Quick Start

### Prerequisites

- Node.js ≥ 20
- pnpm ≥ 9 (`npm install -g pnpm`)
- [Obsidian](https://obsidian.md) (for content editing)

### 1. Clone and Install

```bash
git clone https://github.com/snap-star/JTM020-Docs.git
cd JTM020-Docs
pnpm install
```

### 2. Start Dev Server

```bash
pnpm dev
# → http://localhost:4321
```

### 3. Open Obsidian Vault

1. Open **Obsidian**
2. Click **Open folder as vault**
3. Select `src/content/` inside this repo
4. The VaultCMS plugin loads automatically with a pre-configured dashboard

---

## 📝 Writing Documentation

### Via Obsidian (Recommended)

| Shortcut                               | Action                        |
| -------------------------------------- | ----------------------------- |
| `Ctrl+Shift+N`                       | Create new documentation post |
| `Ctrl+Shift+H`                       | Open CMS dashboard            |
| `Ctrl+E`                             | Toggle editor/preview         |
| `Ctrl+P` → `Git: Commit and push` | Publish your changes          |

### Via CLI

```bash
pnpm new-post my-doc-title
# Creates: src/content/posts/my-doc-title.md
```

### Frontmatter Reference

```yaml
---
title: My Documentation Page
published: 2025-01-01
description: Brief summary shown in previews and search.
image: ""
tags: [API, Reference]
category: Reference
draft: false
---
```

---

## 🗂️ Project Structure

```
JTM020-Docs/
├── src/
│   ├── config.ts
│   ├── content/
│   │   ├── .obsidian/         # Obsidian vault config (VaultCMS)
│   │   ├── _bases/
│   │   │   ├── Home.base      # CMS dashboard
│   │   │   └── templates/     # New post templates
│   │   └── posts/             # ← Write your docs here
│   ├── pages/
│   └── components/
├── .github/
│   └── workflows/
│       └── deploy.yml         # Auto-deploy to GitHub Pages
├── astro.config.mjs
└── package.json
```

---

## 🔧 Configuration

Edit `src/config.ts`:

```ts
export const siteConfig: SiteConfig = {
  title: "JTM020-Docs",
  subtitle: "Technical Documentation Hub",
  themeColor: { hue: 220 },
  toc: { enable: true, depth: 3 },
};
```

---

## 🚢 Deployment

### GitHub Pages (Included)

Push to `main` → auto-deploys via GitHub Actions.

**First-time setup:**

1. Go to **Settings → Pages**
2. Set Source to **GitHub Actions**
3. Push any commit to trigger deployment

---

## 🧩 VaultCMS Plugin Setup

Since VaultCMS is a beta plugin, install via BRAT:

1. Install **BRAT** from Obsidian Community Plugins
2. In BRAT → **Add Beta Plugin** → `https://github.com/davidvkimball/obsidian-vault-cms`
3. Enable the plugin
4. Command Palette → `Vault CMS: Open setup wizard`

---

## 📄 License

MIT

*Built with [Fuwari](https://github.com/saicaca/fuwari) · Managed with [VaultCMS](https://vaultcms.org) · Deployed on [GitHub Pages](https://pages.github.com)*
