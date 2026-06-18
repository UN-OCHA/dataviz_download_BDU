# OCHA Humanitarian DataViz Tool — Download

This repository hosts the **download form** for the OCHA Humanitarian DataViz
Tool, a free plugin for Adobe Illustrator for building OCHA-branded charts, made
by the OCHA Brand and Design Unit (BDU).

**Live form:** https://un-ocha.github.io/dataviz_download_BDU/
**Used on:** embedded in the brand portal page
https://brand.unocha.org/document/474320 (Humanitarian DataViz Tool) via
Frontify's native Embed block.

## What it does

Visitors enter their **name, email, and organization**, then receive the
download. This lets the BDU understand who is using the tool and which
organizations it is reaching (the in-app analytics are anonymous; this captures
identity once, at download).

## How it works

- A single static page (`index.html`) served by **GitHub Pages**. Because it's
  embedded inside the Frontify page (which provides the surrounding context),
  the page itself is header-free: a short title, the three fields, the button,
  and a UN-aligned privacy note.
- On submit it posts the three fields to a **Google Apps Script** backend with
  `credentials: 'omit'` (cookie-less) — this makes Google treat the request as
  anonymous, which sidesteps the multi-account `/u/N/` routing error that broke
  the earlier Apps-Script-hosted version. It then redirects to the Dropbox
  download.
- The backend (a separate Apps Script project owned by the BDU team account)
  appends each entry to the **Downloads** tab of the analytics Google Sheet,
  emails **ochavisual@un.org**, and the sheet's **Dashboard** tab summarizes
  downloads (total, organizations reached, and a by-organization breakdown).

To change the form, edit `index.html` and commit — GitHub Pages redeploys
automatically (~1–2 min) and the Frontify embed picks it up on next load.

## Project Owner
Javier Cueto, Lead — Brand and Design Unit (BDU), OCHA

## Maintained by
**OCHA Brand and Design Unit (BDU)**
- Team: ochavisual@un.org
- Focal point: Javier Cueto (cuetoj@un.org)
