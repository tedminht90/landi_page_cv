# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal portfolio landing page for Tạ Minh Trí (DevSecOps & SRE Engineer). The entire site is a **single self-contained file**: `index.html`.

## Development

No build step, package manager, or toolchain is needed. Open `index.html` directly in a browser or serve it with any static file server:

```bash
# Python
python3 -m http.server 8080

# Node.js (if available)
npx serve .
```

## Architecture

Everything lives in `index.html`:

- **Styles** (`<style>` block, lines 12–273): Custom CSS animations layered on top of Tailwind CDN classes. Key animation classes: `.gradient-bg`, `.glow`, `.skill-tag`, `.timeline-item`, `.float`, `.typing`, `.project-card`, `.particle`, `.star`.
- **Markup** (lines 275–1419): Sections in order — Header/Nav → Hero → About → Experience (timeline) → Skills → Projects → Certifications/Education → Contact form → Footer.
- **Scripts** (`<script>` block, lines 1420–1557): Vanilla JS for particles, constellation stars, mobile menu toggle, contact form (simulated — no backend), smooth scroll, IntersectionObserver for timeline animations, header scroll behavior, typing effect restart loop.

## Key Dependencies (CDN, no install)

- **Tailwind CSS** — utility classes via CDN (`https://cdn.tailwindcss.com`)
- **Inter font** — Google Fonts

## Content Files

- `TaMinhTri_20260108.docx` / `.pdf` — CV/resume documents (latest version)
- `TaMinhTri_20250709.docx` / `.pdf` — Previous CV versions (deleted from git tracking per git status)

## Notes

- The contact form (`#contact-form`) does **not** send real email — it simulates submission with `setTimeout`. To make it functional, integrate a backend service (e.g., AWS SES, Formspree, EmailJS).
- Profile image is loaded from a CloudFront URL (`d1nprcww96gwhv.cloudfront.net`). If it goes offline, replace `src` on lines 397 and 529.
- Color palette is indigo/purple/pink gradient throughout. Maintain this palette when adding new sections or tags.
