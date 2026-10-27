# NYTA Contracting website

A one-page website for NYTA Contracting Ltd., built with [Astro](https://astro.build). Astro turns the files in `src/` into plain HTML, CSS and images in a `dist/` folder, which any static host (Vercel, Netlify, etc.) can serve.

## Where things are

| What you want to change | File |
| --- | --- |
| Text, services, FAQ, phone, Calendly link | `src/pages/index.astro` (lists at the top, HTML below) |
| Colours, fonts, spacing, animations | `src/styles/global.css` (colours are variables at the top) |
| Page title, Google/social sharing info | `src/layouts/Layout.astro` |
| Logo | `src/assets/` (converted to WebP automatically) |
| Favicon and social sharing image | `public/` |
| Live domain name (currently `https://nytacontracting.com`) | `astro.config.mjs` |

## Run it on your computer

You need [Node.js](https://nodejs.org) version 22.23.4 or newer (24 recommended).

```bash
npm install      # first time only
npm run dev      # opens a live preview at http://localhost:4321
npm run build    # makes the final site in dist/
```

## Deploy on Vercel

1. In Vercel, click **Add New → Project** and pick this GitHub repo.
2. Vercel detects Astro on its own. Keep the default settings and click **Deploy**.

## Connect the quote form (must be done before launch)

> **Right now the quote form does not send anything.** NYTA has no email address listed, so there is nowhere to send requests yet. When a visitor presses "Request free quote", the site shows: *"Our online form isn't connected yet. Please call us at (778) 865-5998."*

To make it work:

1. Get an email address from the client that should receive quote requests.
2. Make a free form at [formspree.io](https://formspree.io), sent to that address.
3. Copy the form URL (looks like `https://formspree.io/f/abcdwxyz`).
4. In `src/pages/index.astro`, paste it into `const FORM_ENDPOINT = '';`.
5. Send a test request from the live site and check it arrives.

Once connected, visitors see a thank-you message after sending. If sending fails, they see a message asking them to call.

## Still to confirm with the client

- **Email address:** none was listed on their current site. Needed for the form (see above).
- **Project photos:** the biggest upgrade available. Add a gallery section once they have photos.
- **Domain:** check the site will live at nytacontracting.com (set in `astro.config.mjs`).

## Undoing a change

Every change is a separate git commit. To undo the most recent one safely (this keeps history):

```bash
git revert HEAD
```
