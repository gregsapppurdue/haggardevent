# Meet Craig Haggard — RSVP

Single-page invitation and RSVP form for a neighborhood meet-and-greet with **Craig Haggard**, candidate for Indiana's 4th Congressional District.

- **When:** Saturday, April 25, 2026 · 11:00 am – 1:00 pm
- **Where:** 400 N 9th St Rd, Apt 404, Lafayette, IN 47904
- **Hosts:** Gregory Sapp & Heath Murray

## Live site

Enable GitHub Pages on this repo (Settings → Pages → Deploy from branch → `main` / `root`) and the invitation will be served at:

`https://gregsapppurdue.github.io/haggardevent/`

## How it works

- `index.html` is a fully self-contained static page — HTML, CSS, and JS inline. No build step, no dependencies beyond Google Fonts (Oswald + Barlow) loaded from CDN.
- Form submissions POST to a Google Apps Script Web App, which appends each RSVP as a row in a private Google Sheet and emails the host.
- If the POST fails for any reason, the page gracefully falls back to opening the guest's email client with a pre-filled RSVP message.

## Editing

Open `index.html` in any editor. The styling lives in a single `<style>` block near the top; the submission logic is in the `<script>` block at the bottom.
