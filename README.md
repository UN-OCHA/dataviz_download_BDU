# OCHA Humanitarian DataViz Tool — Download

This repository hosts the **download form** for the OCHA Humanitarian DataViz
Tool, a free plugin for Adobe Illustrator for building OCHA-branded charts, made by
the OCHA Brand and Design Unit (BDU).

**Live form:** https://un-ocha.github.io/dataviz_download_BDU/

## What it does

Visitors enter their **name, email, and organization**, then receive the
download. This lets the BDU understand who is using the tool and which
organizations it is reaching (the in-app analytics are anonymous; this captures
identity once, at download).

## How it works

- A single static page (`index.html`) served by **GitHub Pages** — OCHA-branded,
  with the logo embedded so there are no external dependencies.
- On submit it posts the three fields to a **Google Apps Script** backend
  (cookie-less, so visitors signed into multiple Google accounts are treated as
  anonymous and avoid Google's account-routing errors), then redirects to the
  Dropbox download.
- The backend appends the entry to a private Google Sheet and emails the team.

To change the form, edit `index.html` and commit — GitHub Pages redeploys
automatically. The backend lives in a separate Google Apps Script project owned
by the BDU team account.

## Project Owner
Javier Cueto, Lead — Brand and Design Unit (BDU), OCHA

## Maintained by
**OCHA Brand and Design Unit (BDU)**
- Team: ochavisual@un.org
- Focal point: Javier Cueto (cuetoj@un.org)
