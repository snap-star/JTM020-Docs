---
title: Setting Up VaultCMS with Obsidian
published: 2025-01-02
description: Complete guide for configuring VaultCMS and Obsidian to manage content on JTM020-Docs.
image: attachments/obsidian-home-cms.png
tags:
  - VaultCMS
  - Obsidian
  - CMS
  - Setup
category: Setup
draft: false
---

# VaultCMS + Obsidian Integration

VaultCMS turns your **Obsidian vault** into a powerful headless CMS for this Astro site. This means you write documentation in Obsidian's rich editor and it becomes a live, searchable website.

## Architecture Overview

```
Obsidian Vault (src/content/)
       ↓  write markdown + frontmatter
   VaultCMS Plugin
       ↓  manages structure & metadata
   Git push to GitHub
       ↓  triggers CI/CD
   Deployed Astro Site
```

## Prerequisites

- [Obsidian](https://obsidian.md) installed
- [Git](https://git-scm.com) installed
- Repository cloned from [github.com/snap-star](https://github.com/snap-star)

## Installation Steps

### 1. Clone the Repository

```bash
git clone https://github.com/snap-star/JTM020-Docs.git
cd JTM020-Docs
pnpm install
```

### 2. Open Vault in Obsidian

1. Open Obsidian
2. Select **Open folder as vault**
3. Navigate to and select `src/content/` inside the cloned repo
4. Obsidian will load with VaultCMS preconfigured

### 3. Install VaultCMS Plugin (if not auto-detected)

The `.obsidian` folder bundled in `src/content/` contains all required plugin configs. If they don't load:

1. Open **Settings → Community plugins**
2. Install **BRAT** (Beta Reviewers Auto-update Tester)
3. In BRAT, add: `https://github.com/davidvkimball/obsidian-vault-cms`
4. Enable the plugin
5. Run the Setup Wizard via Command Palette: `Open setup wizard`

### 4. Configure Content Types

The wizard auto-detects:
- `posts/` → Blog/documentation posts
- Frontmatter properties: `title`, `published`, `description`, `tags`, `category`, `draft`

## Writing Documentation

### Create a New Doc

Use the command palette (`Ctrl+P` / `Cmd+P`):
```
Astro Composer: New post
```

This inserts the correct frontmatter template.

### Frontmatter Reference

```yaml
---
title: My Documentation Page
published: 2025-01-01
description: Brief description for SEO and previews.
image: ""          # Optional: path to cover image
tags: [Tag1, Tag2]
category: Reference
draft: false       # Set true to hide from production
---
```

### Admonitions (Callout Boxes)

```markdown
> [!note]
> This is a note callout.

> [!tip]
> A helpful tip for readers.

> [!warning]
> Watch out for this!

> [!important]
> Critical information here.
```

## Publishing Workflow

1. Write or edit content in Obsidian
2. Set `draft: false` when ready to publish
3. Commit and push:
   ```bash
   git add src/content/
   git commit -m "docs: add new documentation page"
   git push origin main
   ```
4. GitHub Actions deploys the site automatically

## VaultCMS Home View

The `_bases/Home.base` file provides a **visual CMS dashboard** inside Obsidian:
- Grid view of all documentation pages
- Filter by `draft`, `category`, or `tags`
- Bulk-publish or bulk-update frontmatter

Open it from the **Bases** sidebar icon or via Command Palette: `Bases: Open Home`.
