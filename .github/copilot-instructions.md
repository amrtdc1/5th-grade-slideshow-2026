# GitHub Copilot Instructions — 5th Grade Slideshow 2026 Landing Page

## Project Overview

This repository contains a **landing page** (`index.html`) designed for parents of a 5th-grade class at an elementary school. The landing page provides parents with easy access to a Google Drive folder containing two keepsake files:

1. **Interactive Slideshow App** (`slideshow.html`) — A self-contained HTML application that loads 200+ JPEG photos and 4 MP4 music files into the browser's IndexedDB. It lets users play a slideshow or freely pan/zoom a canvas to explore photos. Takes 10–20 seconds to load on first open.
2. **Slideshow Video** (`slideshow.mp4`) — An MP4 video of the full slideshow presentation with music, exported from the 5th Grade Awards Ceremony. Easier for casual viewing.

The Google Drive folder link, school name, logo, and colors are all **placeholder values** in the code that the developer updates for each deployment. Look for comments marked with `<!-- TODO: UPDATE -->` in the HTML.

---

## Technology Stack

- **Plain HTML5 + CSS3 + vanilla JavaScript** — no build tools, no frameworks, no npm required.
- The page must be **self-contained in `index.html`** (CSS in `<style>` tags, JS in `<script>` tags) unless the developer explicitly asks to split files.
- If a CSS or JS file is added, update `index.html` to reference it.
- Google Fonts (`Poppins`, `Inter`) are loaded via `<link>` tags; assume internet connectivity for viewers.
- No external JavaScript frameworks (React, Vue, etc.) unless the developer explicitly requests one.

---

## Design System

### Color Palette (School Colors — update per school)
```css
--color-primary:    #003087;   /* Deep Navy Blue — school primary */
--color-secondary:  #FFB81C;   /* Gold/Amber — school secondary */
--color-accent:     #e74c3c;   /* Red accent for highlights */
--color-bg:         #f0f4f8;   /* Page background */
--color-surface:    #ffffff;   /* Card / panel background */
--color-text:       #1a1a2e;   /* Body text */
--color-text-muted: #6b7a8d;   /* Secondary/muted text */
```

> 🎨 **To change school colors**, update the CSS custom properties inside `:root` in `index.html`. All components inherit from these variables.

### Typography
- **Headings**: `'Poppins', sans-serif` — weights 600 and 700
- **Body**: `'Inter', sans-serif` — weight 400 and 500
- Base font size: 16px; use `rem` units for type scale.

### Spacing
- Use multiples of 8px for margins/padding (8, 16, 24, 32, 48, 64, 96px).
- Cards use `border-radius: 16px` with `box-shadow`.

### Responsiveness
- Mobile-first breakpoints: `480px`, `768px`, `1024px`, `1280px`.
- Use CSS Grid for layout sections; Flexbox for component-level alignment.
- All interactive elements must be touch-friendly (min 44px tap target).

---

## File Structure

```
5th-grade-slideshow-2026/
├── index.html                   # Main landing page (single source of truth)
├── README.md                    # Project readme
├── .gitignore
└── .github/
    └── copilot-instructions.md  # ← You are here
```

Future additions the developer may ask for:
- `assets/` — school logo image, favicon
- `styles.css` — if CSS is split out
- `scripts.js` — if JS is split out

---

## Key Placeholders in `index.html`

| Placeholder | Description |
|---|---|
| `YOUR SCHOOL NAME` | Replace with the actual school name |
| `YOUR SCHOOL MASCOT / MOTTO` | Replace with mascot or motto |
| `https://drive.google.com/YOUR_FOLDER_LINK` | Replace with the actual Google Drive folder URL |
| `YOUR_LOGO_URL` | Path/URL to the school logo image |
| `Teacher Name` | 5th grade teacher's name |
| `School Year` | e.g., `2025–2026` |

---

## Content Details

### File 1: Interactive Slideshow App (`slideshow.html`)
- HTML file, ~self-contained, runs in any modern browser (Chrome, Firefox, Safari, Edge)
- **First load**: takes 10–20 seconds while hydrating IndexedDB with 200+ JPEG images and 4 MP4 music files
- **After hydration**: loads instantly on subsequent opens (data cached in browser)
- **Two modes**:
  - 🎬 **Slideshow mode**: auto-plays through photos with music
  - 🔍 **Explore mode**: free-roam canvas — pinch/zoom or scroll-wheel to zoom, click/drag to pan
- Best experienced on desktop/laptop; also works on tablets

### File 2: Slideshow Video (`slideshow.mp4`)
- Standard MP4 video — plays in any video player or browser
- The same presentation shown at the 5th Grade Awards Ceremony, with music
- Easiest way to watch; no waiting, no setup
- Can be downloaded and kept as a keepsake

---

## Tone & Messaging Guidelines

- **Audience**: Parents of elementary-school children; warm, celebratory, nostalgic tone
- **Key emotions to evoke**: pride, nostalgia, excitement, community
- **Avoid**: technical jargon (explain IndexedDB as "caching photos in your browser")
- **Emphasize**: this is a **keepsake** — a memento of the child's 5th-grade year
- Use ✨🎓📸🎶 emoji sparingly in headings/labels for a fun, celebratory feel

---

## Development Guidelines

- Keep `index.html` readable — use semantic HTML5 elements (`<header>`, `<main>`, `<section>`, `<footer>`, `<article>`, `<nav>`)
- Add `aria-label` and `role` attributes for accessibility
- Maintain CSS custom properties (variables) for easy theming
- Avoid inline styles; use CSS classes
- Test visually at 375px (mobile), 768px (tablet), and 1280px (desktop) widths
- Ensure the Google Drive button is clearly visible above the fold on all screen sizes

---

## Suggested Future Enhancements

1. **Countdown timer** to the last day of school or graduation ceremony
2. **Photo gallery preview** — embed 3–4 sample photos from the Google Drive folder (if publicly accessible)
3. **Video embed** — embed the MP4 slideshow video directly in the page using `<video>` tag or a preview thumbnail linking to Drive
4. **Print-friendly version** — a minimal printable flyer with the QR code and Drive link
5. **QR code** — generate and embed a QR code linking to the Google Drive folder for easy mobile access
6. **Email share button** — mailto link pre-filled with the Drive folder URL
7. **Analytics** — simple privacy-friendly hit counter (e.g., GoatCounter) to see how many parents visited
8. **Dark mode** — using `prefers-color-scheme` media query
9. **Localization** — Spanish translation for ESL families
10. **Service Worker / PWA** — allow parents to "install" the landing page as a PWA

---

## Instructions for Copilot Chat

When the developer asks you to:

- **Update the school name/colors/logo**: modify the `:root` CSS variables and `<!-- TODO: UPDATE -->` placeholders in `index.html`
- **Add a new section**: create a new `<section>` inside `<main>` following the existing pattern; add navigation anchor if needed
- **Add a feature from the suggestions list**: implement it in the existing `index.html` unless it requires a new file
- **Generate a QR code**: use a JavaScript QR code library (e.g., `qrcode.js` from CDN) injected inline
- **Add animations**: use CSS `@keyframes` or the `Intersection Observer API` for scroll-triggered animations
- **Optimize for print**: add a `@media print` CSS block
- **Change fonts**: update the Google Fonts `<link>` and the `--font-heading` / `--font-body` variables

Always preserve the existing HTML structure and CSS variable system when making additions.
