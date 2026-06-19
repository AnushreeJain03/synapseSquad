# Skill Issue

A tiny static website that shows **"Skill issue"** in big letters in the middle of the page.

## Files

- `index.html` — the page
- `style.css` — the styling (centering + big text)

There is **no backend** — it's just static files, so any web host can serve it.

## How to put it on your IONOS domain

You have two common options with IONOS.

### Option A — IONOS Web Hosting / "Deploy Now" (upload the files)

1. Log in to IONOS → **Hosting** (or **Websites & Stores**).
2. Open the **File Manager** (or connect via SFTP/FTP — IONOS shows the
   host, username, and password under your hosting package's SFTP settings).
3. Upload `index.html` and `style.css` into the web root folder
   (usually called `/` , `htdocs`, or `public`).
4. Make sure your domain points at this hosting package
   (IONOS → **Domains** → assign the domain to the hosting / set it as the
   home directory).
5. Visit your domain — done.

### Option B — Host on GitHub Pages, point IONOS domain at it (free)

1. Push this repo to GitHub (it already is).
2. In the repo: **Settings → Pages →** Source = your branch, folder = `/root`.
3. GitHub gives you a `*.github.io` URL. Confirm the site works there.
4. Add your custom domain in **Settings → Pages → Custom domain** and enter
   your IONOS domain.
5. In IONOS → **Domains → DNS**, add the records GitHub asks for:
   - Four `A` records pointing to GitHub's IPs:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - (For `www`) a `CNAME` record pointing to `<your-username>.github.io`.
6. Wait for DNS to propagate (minutes to a few hours), then enable
   "Enforce HTTPS" in GitHub Pages.

## Want an image instead of / above the text?

Drop the image file into this folder and uncomment the `<img>` line in
`index.html`, updating the filename.
