# Kometa — Sitio web oficial

React + Vite. Single-page site with the Nosotros, Resultados, Servicios, Naming, Registro de marca,
Branding, Presencia digital, Estrategia de contenidos, Campañas publicitarias, Automatización,
Portafolio, Equipo, and Contacto sections.

## Run it locally

You need [Node.js](https://nodejs.org) 18 or newer.

```bash
npm install
npm run dev
```

Open the URL it prints (usually `http://localhost:5173`). Changes to any file in `src/` hot-reload
automatically.

To check the production build locally before deploying:

```bash
npm run build
npm run preview
```

## Deploy to Vercel

**Option A — from the Vercel dashboard (no terminal needed)**
1. Push this folder to a GitHub repo.
2. Go to [vercel.com/new](https://vercel.com/new) and import that repo.
3. Vercel auto-detects Vite — leave the build command (`vite build`) and output directory (`dist`)
   as suggested. Click Deploy.

**Option B — from the terminal**
```bash
npm install -g vercel
vercel
```
Follow the prompts. Running `vercel` again (or `vercel --prod`) after making changes redeploys.

## Project structure

```
index.html              ← page shell, SEO/social meta tags, favicon links
src/
  main.jsx               ← React entry point
  App.jsx                ← the whole site (nav, sections, all components)
  index.css               ← all styles (fonts, colors, layout, animations)
  assets/images/           ← every real image the site uses, organized by section
public/
  favicon.ico, favicon-*.png, apple-touch-icon.png, android-chrome-*.png
  site.webmanifest        ← home-screen icon config
  og-image.jpg             ← social share preview image
```

## Things worth knowing before you hand this to a developer

- **Content source**: nearly all copy, step lists, and images were pulled directly from
  `Brochure_kometa.pdf`. A few short section intros/taglines were written to connect sections and
  are noted as such where it came up during review — worth a final copy pass.
- **Contact info**: address, phone, email, and social links are wired to real values (WhatsApp
  deep link, Instagram, Facebook, TikTok, YouTube). Double check the WhatsApp number and email
  before launch.
- **Animations**: built with plain CSS transitions + `IntersectionObserver` (no animation library
  dependency). If you want more elaborate motion later (spring physics, gesture-based interactions),
  swapping in Framer Motion is a natural next step — the component structure doesn't need to change
  for that.
- **Images**: everything is a real imported file (not inline base64), so Vite will hash, compress,
  and cache them properly on build. Total image payload is ~2MB across 58 files.
