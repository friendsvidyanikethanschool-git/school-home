# Friends Vidyanikethan High School — Website

Static site for the school — About, Academics, Admissions, Facilities,
Gallery, Notices, Portals (ERP, Payroll, Inventory, Digital Library and
more) and Contact, all in one page. No backend server — just HTML, CSS
and JS served as static files, plus a small `/admin/` page that edits
content through GitHub's API.

## Files

```
index.html          The whole public site
admin/index.html     Admin page — edit content.json and notices.json without touching code
content.json         Editable content: portal links, stats, principal message, admissions
                      buttons, downloads, gallery, achievements, office hours
notices.json         Notice board entries
assets/logo.png      School logo, background removed
assets/gallery/       Gallery photos land here when added via the admin page
assets/downloads/     Downloadable files land here when added via the admin page
PORTALS.md           Working notes on each portal's scope and access — fill in as you build
.nojekyll             Tells GitHub Pages to skip Jekyll processing (leave this as is)
CNAME.example         Notes for the custom domain step — see below
```

## Editing content — two ways

### The admin page (no code, no raw JSON)

Open `admin/index.html` in a browser once the site is live — e.g.
`https://friendsvidyanikethanschool-git.github.io/school-home/admin/`.

1. Enter the GitHub org, repo name, branch (`main`), and a **Personal
   access token** with write access to this repo. The page tells you
   exactly how to create one and what permission it needs.
2. Click **Connect & load** — every editable section fills in with the
   current content.
3. Edit a section and click its **Save** button. That section commits
   straight to the repo; GitHub Pages rebuilds automatically (usually
   under a minute).

From the admin page you can:
- Add, edit or remove notices
- Set the URL for each portal card (ERP, Digital Library, Learning
  Portal, Parent Portal, Staff Webmail — Payroll and Inventory are
  already set)
- Set the four homepage statistics
- Set the Principal's name, message and photo
- Set the three Admissions buttons (enquiry link, form upload, apply link)
- Upload files for the six Downloads items
- Add or remove Gallery photos
- Edit the five Achievements descriptions
- Set office hours

The token is only kept in that browser tab and is never saved anywhere
— close the tab and it's gone, so you'll enter it again next time. If
you're on a shared computer, revoke the token on GitHub when you're done.

### Editing the JSON files directly

Everything the admin page writes lives in two plain files,
`content.json` and `notices.json`. You can also open either on GitHub
(click the file → pencil icon) and edit it by hand if you'd rather —
the admin page is just a friendlier way to do the same thing. Neither
approach ever touches `index.html`.

## 1. Put this on GitHub

1. Create a new repo in the `friendsvidyanikethanschool-git` org — e.g. `school-home`.
2. Upload every file in this folder, keeping the folder structure intact
   (`assets/`, `admin/`, and the JSON files at the root, alongside `index.html`).
3. Commit to the `main` branch.

## 2. Turn on GitHub Pages

1. In the repo: **Settings → Pages**.
2. Under "Build and deployment", set **Source** to `Deploy from a branch`.
3. Branch: `main`, folder: `/ (root)`. Save.
4. GitHub gives you a live URL, typically:
   `https://friendsvidyanikethanschool-git.github.io/school-home/`
   It can take a minute or two to go live the first time.

## 3. Fill in what's still placeholder

Use the admin page (above) for portal links, stats, principal message,
admissions buttons, downloads, gallery and achievements. A few things
are still fixed in `index.html` itself and need a direct edit if they
change: the school's address/phone/email in the footer and Contact
section, the classes offered, and the board affiliation/school timings
in Academics.

## 4. Once you buy the domain

1. At your domain registrar, add a DNS record pointing to GitHub Pages:
   - For an apex domain (e.g. `yourschool.in`): four `A` records pointing to GitHub's Pages IP addresses (GitHub's docs list the current ones — search "GitHub Pages A records").
   - For a subdomain (e.g. `www.yourschool.in`): a `CNAME` record pointing to `friendsvidyanikethanschool-git.github.io`.
2. In the repo, add a file named exactly `CNAME` (no extension) at the root, containing only your domain on one line, e.g.:
   ```
   www.yourschool.in
   ```
   (See `CNAME.example` in this folder for the format — rename/replace it once you have the real domain.)
3. Back in **Settings → Pages**, enter the same domain in the "Custom domain" field and save. Optionally tick "Enforce HTTPS" once GitHub finishes issuing a certificate (can take a few hours).

DNS changes can take anywhere from a few minutes to 24–48 hours to fully propagate.
