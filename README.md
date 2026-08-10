# Masanso David — Engineering Portfolio

A single-page, 5-section engineering portfolio for Masanso David (Software & Systems Engineer),
built with HTML5, Tailwind CSS (CDN), custom CSS variables, and vanilla JavaScript.

**Design direction — "Field Terminal / PCB Trace":** a blueprint-dark (or warm-paper light)
engineering aesthetic built around a signature vertical trace rail on desktop that lights up
node-by-node as you scroll through the five sections (01–05), plus a typed terminal boot-log
in the hero. Type is set in Space Grotesk (display), IBM Plex Sans (body), and IBM Plex Mono
(data/labels/badges) — cyan-teal as the primary signal color, amber as a sparing hazard-tape
accent. Automatic dark/light theme detection with a persistent manual toggle, smooth in-page
navigation, and a mobile drawer menu.

## Folder structure

```
masanso-portfolio/
├── index.html                     ← the entire site (all styles + scripts embedded)
├── assets/
│   ├── images/
│   │   ├── hero-portrait.jpg      ← Home hero photo
│   │   └── about-portrait.jpg     ← About section photo
│   └── cv/
│       └── masanso-david-cv.pdf   ← downloadable from the Contact section
└── README.md
```

## Hosting on GitHub Pages

1. Create a new GitHub repository (e.g. `masanso-portfolio`).
2. Push the **contents of this folder** to the repository root — `index.html` must sit at the
   repo root (or in `/docs` if you prefer that Pages source option).
   ```bash
   git init
   git add .
   git commit -m "Initial portfolio commit"
   git branch -M main
   git remote add origin https://github.com/Masa010pro/masanso-portfolio.git
   git push -u origin main
   ```
3. In the repo: **Settings → Pages → Build and deployment → Source** → select `Deploy from a
   branch`, branch `main`, folder `/ (root)`. Save.
4. Your site will be live at:
   `https://masa010pro.github.io/masanso-portfolio/`
5. All image paths are relative (`assets/images/...`), so this works out of the box on both a
   root domain and a `/repo-name/` GitHub Pages subpath — no changes needed.

## CV

Your CV is already included at `assets/cv/masanso-david-cv.pdf` and wired to the "Download CV"
button in the Contact section. To swap in an updated version later, just replace that file
with a new one using the same filename — no HTML changes needed.

## Contact form

The form currently posts to `https://formsubmit.co/masadavid010@gmail.com` — a free,
no-backend form relay. On first submission, FormSubmit sends a one-time confirmation email
to activate the address; after that, submissions arrive as email. If you'd rather use a
different provider (Formspree, Netlify Forms, your own backend, etc.), just swap the `action`
URL on the `<form id="contactForm">` element in `index.html`.

## Customizing theme colors

All color tokens live as CSS custom properties at the top of `index.html` inside
`:root { ... }` (dark mode) and `html.light { ... }` (light mode) — change `--cyan`,
`--indigo`, `--teal`, `--bg`, `--surface`, etc. to retheme the entire site from one place.

## Browser support

Modern evergreen browsers (Chrome, Firefox, Safari, Edge). Uses `prefers-color-scheme` for
automatic theme detection, `IntersectionObserver` for scroll reveals, and respects
`prefers-reduced-motion`.
