# Mariyam.dev: Portfolio Website

Single-page portfolio for **Mariyam Manekiya, Full Stack Developer** (React.js, Python, PHP, WordPress).

The whole site is one self-contained `index.html` file: plain HTML, CSS and JavaScript. It has no build step, no framework and no dependencies.

---

## Folder structure

```
My Portfolio/
├── index.html                  ← the entire website (HTML + CSS + JS)
├── README.md                   ← this file
└── assets/
    ├── Mariyam-Manekiya-Resume.pdf      ← ADD THIS (Download Resume button)
    └── projects/                        ← project screenshots (placeholders now)
        ├── ai-career-copilot.svg
        ├── finance-dashboard-1.svg   …-2.svg   …-3.svg
        ├── wordpress-website-1.svg   …-2.svg   …-3.svg
        ├── restaurant-landing-1.svg  …-2.svg   …-3.svg
        └── small-business-1.svg      …-2.svg   …-3.svg
```

Optional: add `og-image.png` (1200×630) to the root for link previews on WhatsApp, LinkedIn and similar sites.

---

## Before you publish: fill in the placeholders

Everything you need to edit is in `index.html`. Use Ctrl+F to find each item.

| What | Search for | What to do |
|---|---|---|
| Profile links | `const LINKS` | Paste your GitHub, LinkedIn, Fiverr and Freelancer URLs |
| Project links | `const PROJECT_LINKS` | AI Career demo + repo, plus optional video and code links. Empty optional buttons stay hidden |
| Demo login | `[demo email]` / `[demo password]` | Your AI Career Co-Pilot test account |
| Contact form | `const FORMSPREE_ID` | Create a free form at formspree.io and paste the ID (e.g. `xyzabcde`) |
| Prices | `$X` | Six "Starting from" prices in Services. Keep them the same as your Fiverr packages |
| Hero photo | `[HERO PHOTO]` | Replace the placeholder with your `<img>` |
| About photo | `[ABOUT PHOTO]` | Replace the "MM" initials with your `<img>` |
| Screenshots | `assets/projects/` | Save real PNG/JPG screenshots (16:10, ~1600×1000) and update the `src` and `alt` values in the Projects section |
| Resume | `Mariyam-Manekiya-Resume.pdf` | Put your PDF in `assets/` with this exact name |
| Domain | `your-domain.com` | Replace with your live URL after deploying (4 places in `<head>`) |
| Reviews | `CLIENT REVIEWS` | When you get real reviews, follow the template in the HTML comment |

---

## Deploy for free

### Option A: Netlify Drop (easiest, no Git needed)

1. Go to **https://app.netlify.com/drop** and sign up (free; you can use your Google account).
2. Drag the whole **`My Portfolio`** folder onto the page.
3. Wait a few seconds. Netlify gives you a live link like `https://random-name-123.netlify.app`.
4. Rename it: **Site configuration → Change site name** and type e.g. `mariyam-dev`, which gives you `https://mariyam-dev.netlify.app`.
5. **To update later:** open your site in Netlify, go to **Deploys**, and drag the folder onto the drop area again.

### Option B: Vercel (via GitHub, auto-updates on every change)

1. Create a free account at **https://github.com** and click **New repository**. Name it `portfolio`, set it to Public, and click **Create repository**.
2. On the new repo page, click **uploading an existing file**. Drag in `index.html`, `README.md` and the `assets` folder, then click **Commit changes**.
3. Go to **https://vercel.com**, click **Sign up**, and choose **Continue with GitHub**.
4. Click **Add New… → Project**, find your `portfolio` repo and click **Import**.
5. Leave every setting as it is: **Framework Preset: Other**, no build command, no output directory. Click **Deploy**.
6. Your site is live at `https://portfolio-xxxx.vercel.app`. Change the name under **Settings → Domains**.
7. **To update later:** edit or upload files in GitHub, and Vercel redeploys automatically within a minute.

> Netlify can also connect to the same GitHub repo (**Add new site → Import an existing project → GitHub**) if you want auto-updates there instead.

### After deploying

1. Replace `https://your-domain.com/` in the `<head>` of `index.html` with your real link, then redeploy.
2. Open the site on your phone and test: the menu, dark mode, project filters, the gallery, and a test message through the contact form.
3. Put the link on your Fiverr profile, Freelancer profile, LinkedIn and GitHub bio.
4. Optional: buy a custom domain (e.g. `mariyam.dev`) and add it under **Domains** in Netlify or Vercel. HTTPS is free and automatic.

---

## How the code is organised (`index.html`)

1. **`<head>`**: SEO title, description, Open Graph and Twitter tags, JSON-LD, fonts, and the theme script that runs before the page appears.
2. **`<style>`**, in numbered sections: design tokens (colours, fonts, radius), base styles, layout, reusable components (buttons, cards, chips), then one block per page section.
3. **Icon sprite**: every line icon as an SVG `<symbol>`, used with `<use href="#i-name">`.
4. **Page sections, in order**: Navbar → Hero → Services → Projects → Skills → How I Work → Why Work With Me → About → Client Reviews → FAQ → Contact → CTA → Footer.
5. **`<script>`**: `LINKS` and `PROJECT_LINKS` config, theme toggle, mobile menu, scroll animations, active nav link, project filter, lightbox, copy buttons, and the contact form (Formspree, with an email-app fallback).
