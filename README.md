# Marquee-Management-System
Marquee Management System demo


# Shaadi Halls — Deployment Guide

`marquee.html` is a single self-contained file (HTML + CSS + JS, no build step, no server required). It uses the browser's `localStorage` for demo data, so it's ready to host anywhere that serves static files.

## Fastest options (free, 2 minutes)

**Netlify Drop**
1. Go to https://app.netlify.com/drop
2. Drag `marquee.html` onto the page
3. Rename it to `index.html` first if you want it at the root URL (or Netlify will serve it at `/marquee.html`)

**GitHub Pages**
1. Create a new GitHub repo
2. Upload `marquee.html`, rename to `index.html`
3. Repo Settings → Pages → set source to the `main` branch, root folder
4. Live at `https://<your-username>.github.io/<repo-name>/`

**Vercel**
1. `npm i -g vercel` (or use the web dashboard)
2. Put `index.html` (renamed) in a folder, run `vercel` in that folder, follow prompts

**Any shared hosting / cPanel (common with Pakistani hosts like Hostinger, WHC, TrueHost)**
1. Rename `marquee.html` to `index.html`
2. Upload via File Manager or FTP into `public_html/`
3. Visit your domain — done

## Custom domain
Any of the above lets you point a `.pk` or `.com` domain at it via CNAME/A record from your registrar (e.g. PKNIC or Namecheap).

## Important: this is a front-end demo, not a production backend
Everything currently lives in the visitor's own browser (`localStorage`) — so:
- Bookings made on one phone/browser are **not visible** to a vendor on another device.
- There's no real authentication, no real payment processing, and no shared database.

To go live for real bookings, the next step is a backend + database (see the earlier spec: Node.js/NestJS or Laravel + PostgreSQL) with:
- A real API replacing the in-browser `DATA` object
- JazzCash/Easypaisa server-side integration (their APIs require a backend to sign requests securely — this can't be done safely in browser JS)
- Login for vendors and admins

I can build that backend (API + database) as the next step whenever you're ready — just say the word.
