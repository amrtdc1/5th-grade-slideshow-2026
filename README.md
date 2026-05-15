# 5th Grade Slideshow 2026 — Landing Page

A modern, celebratory landing page for parents of a 5th-grade class. It links to a shared Google Drive folder containing two keepsake files: an interactive HTML slideshow app and an MP4 video of the Awards Ceremony presentation.

## Quick Start — Customizing for Your School

Open `index.html` and search for `TODO: UPDATE` comments. There are five things to change:

| What to update | Where |
|---|---|
| School name | `<!-- TODO: UPDATE -->` comments in header, hero, welcome strip, and footer |
| School colors | `:root` CSS variables at the top of the `<style>` block |
| School logo | Replace the `.logo-mark` `<div>` with an `<img>` tag |
| Google Drive URL | All `href="https://drive.google.com/YOUR_FOLDER_LINK"` attributes |
| Teacher name(s) | The `Teacher Name` placeholder in the welcome strip |

## File Structure

```
5th-grade-slideshow-2026/
├── index.html                   # Landing page (single self-contained file)
├── README.md
├── .gitignore
└── .github/
    └── copilot-instructions.md  # AI context for GitHub Copilot sessions
```

## What the Landing Page Contains

- **Hero section** — animated gradient with school branding and a prominent Drive folder CTA
- **Welcome strip** — message from teachers with highlight stats (200+ photos, 4 music tracks)
- **File cards** — detailed cards for both the interactive HTML slideshow and the MP4 video, each with feature lists and important usage notes
- **How It Works** — tabbed step-by-step guide for each file type
- **Drive CTA** — large, unmissable call-to-action section to open the shared folder
- **FAQ** — 8 common questions covering loading times, offline use, browsers, and more
- **Fully responsive** — designed for mobile, tablet, and desktop

## Design System

Colors are controlled by CSS custom properties at the top of `index.html`:

```css
--color-primary:    #003087;   /* School navy blue */
--color-secondary:  #FFB81C;   /* School gold */
```

Change these two variables and the entire page re-themes instantly.

## AI Context

This repo includes `.github/copilot-instructions.md` — a comprehensive context file for GitHub Copilot. Open any file in VS Code and chat with Copilot to:
- Customize school branding
- Add new sections (countdown timer, photo gallery, QR code, etc.)
- Adjust colors, fonts, and layout
- Generate print-friendly versions

## Deployment

The page is a single static HTML file with no build step required. Deploy via:
- **GitHub Pages** — push to `main`, enable Pages in repo settings, set source to root
- **Netlify / Vercel** — drag and drop `index.html`
- **Any web host** — upload `index.html` to your hosting provider
