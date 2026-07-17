# Friends Vidyanikethan High School — Portal Homepage

Static homepage linking the school's ERP, Payroll, Inventory, Digital Library and other applications. No backend — just HTML, CSS and JS, served as static files.

## Files

```
index.html         The whole page (structure, styling and behaviour in one file)
assets/logo.png     School logo, background removed
notices.json        Notice board content — edit this, not the page, to post a notice
PORTALS.md          Working notes on each portal's scope and access — fill in as you build
.nojekyll            Tells GitHub Pages to skip Jekyll processing (leave this as is)
CNAME.example        Notes for the custom domain step — see below
```

## Posting a notice (no code required)

Open `notices.json` on GitHub (click the file → pencil icon to edit) and add a block like:

```json
{
  "date": "2026-08-01",
  "title": "School reopens for Term 2 on 1 August.",
  "tag": "General"
}
```

Add a comma after the previous block, save/commit, and it appears on the homepage automatically — nothing in `index.html` needs to change. Notices are sorted newest-first by the `date` field automatically.

If whoever posts notices shouldn't need a GitHub account at all, a Google Sheet published as JSON is a reasonable alternative — happy to wire that up instead if it'd suit your office staff better.

## 1. Put this on GitHub

1. Create a new repo in the `friendsvidyanikethanschool-git` org — e.g. `school-home`.
2. Upload every file in this folder, **keeping `assets/logo.png` inside an `assets` folder** (the page links to `assets/logo.png`, so the folder structure has to match).
3. Commit to the `main` branch.

## 2. Turn on GitHub Pages

1. In the repo: **Settings → Pages**.
2. Under "Build and deployment", set **Source** to `Deploy from a branch`.
3. Branch: `main`, folder: `/ (root)`. Save.
4. GitHub gives you a live URL, typically:
   `https://friendsvidyanikethanschool-git.github.io/school-home/`
   It can take a minute or two to go live the first time.

## 3. Fill in the placeholder links

Search `index.html` for `href="#"` — each marks a portal card that isn't wired up yet (ERP, Digital Library, Learning Portal, Parent Portal, Staff Webmail). Replace `#` with the real URL as each system goes live. Payroll and Inventory are already wired to their GitHub Pages URLs.

Also replace the placeholder address, phone number and email in the footer.

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
