# Product migration tracker

A generic, single-file tracker for comparing capabilities across a source product,
a target product, and another host. Includes an editable project board, role-based
views, phase tracking, bug bashes, communications, leadership asks, and a comparison
table with filtered PNG export.

## What this repository contains

`index.html` is a sanitized derivative of an earlier tracker, not a backup or mirror
of a production application. It contains one fictional example feature. Internal
meeting summaries, people, links, feature plans, delivery dates, and production data
have been removed. No live-data export or authentication files are included.

Availability and release-scope fields start as TBD. Populate them explicitly rather
than treating the sample as a statement about any real product.

## Run locally

Open `index.html` in a browser. Edits are saved in that browser's local storage.
Alternatively, with Python installed:

```powershell
python -m http.server 8080 --bind 127.0.0.1
```

Open `http://127.0.0.1:8080`. Without a compatible backend, the app displays
**Local only**. No build step, package installation, or external UI library is needed.

## Shared hosting

The optional shared backend uses root-relative `/api/data/tracker` requests and
`/api/userinfo`. On Joust, those endpoints belong to the app from which this page is
served. Credentials are managed by Joust and must never be embedded in the HTML.

If you have the Joust skill and access to its hosting service, publish a separate
app under your own account:

```powershell
node "$HOME\.copilot\skills\joust\scripts\joust.mjs" login
node "$HOME\.copilot\skills\joust\scripts\joust.mjs" publish --dir . --app your-tracker-name --non-interactive
```

Choose your own app name. Publishing to an existing app replaces its frontend.
Review the hosting service's access and data-handling rules before entering data.
This repository does not grant access to, or deployment rights over, another app.

Do not connect a personal deployment to a company production database or import
internal tracker exports into this repository.

## Continue development

Clone this repository and edit `index.html`; CSS and JavaScript are inline. After
changes, check the board, capability drawer, Bug Bash, Communications, LT Board,
and filtered PNG export. Test storage changes against a separate test app.

Several internal schema keys (`ab`, `mcs`, `spo`) are retained for compatibility;
they represent the generic hosts displayed above, not real product commitments.

Invite collaborators through the repository's **Settings > Collaborators** page.
Each collaborator must accept the invitation before using their granted access.
