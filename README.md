# cbadea.com — personal academic site

A single-file static site. Deploys to GitHub Pages with a custom domain.

## Files
- `index.html` — the whole site (HTML + embedded CSS).
- `CNAME` — tells GitHub Pages to serve this site at `cbadea.com`.
- `README.md` — this file.

## How to deploy (one-off, ~15 minutes)

### 1. Buy the domain
- Go to Namecheap (or your registrar of choice).
- Search `cbadea.com`. Apply promo code `NEWCOM679` for the first-year discount.
- Buy. Skip the upsells (privacy is included).

### 2. Create a GitHub account and a new repo
- If you don't have a GitHub account: sign up at github.com using `cos@ethicos.co.uk` or a personal email.
- Create a new repository, public, named `cbadea-website` (or whatever you like).
- Don't add a README during creation — we have one.

### 3. Upload the three files
- On the new repo page, click "uploading an existing file".
- Drag `index.html`, `CNAME`, and `README.md` from the `website/` folder.
- Commit with a message like "Initial site".

### 4. Turn on GitHub Pages
- In the repo, go to Settings → Pages (left sidebar).
- Under "Source", choose "Deploy from a branch", select branch `main` and folder `/` (root).
- Save. The site will be live at `https://<your-username>.github.io/cbadea-website/` within a minute or two.
- After a few seconds, the "Custom domain" field should populate with `cbadea.com` (read from the CNAME file). Tick "Enforce HTTPS" once the option becomes available — this can take up to 24 hours.

### 5. Point the domain at GitHub Pages
At Namecheap, in your domain's DNS settings, add these records:

```
Type      Host      Value                        TTL
A         @         185.199.108.153              Automatic
A         @         185.199.109.153              Automatic
A         @         185.199.110.153              Automatic
A         @         185.199.111.153              Automatic
CNAME     www       <your-username>.github.io    Automatic
```

DNS changes propagate in 10 minutes to a few hours. Visit `cbadea.com` after that — should load the site.

## Updating later
Edit `index.html` directly in GitHub's web editor (pencil icon). Commit. Site updates within a minute. No build step.

## Adding things later (optional)
- A "Talks" section under "Teaching".
- Links to PDFs of papers (drop them in the repo, link with `<a href="paper.pdf">`).
- A photo: put `photo.jpg` in the repo, add `<img src="photo.jpg" alt="Cosmin Badea" style="width:140px; border-radius:50%;">` near the top of `<header>`.
- Google Scholar URL: replace the `https://scholar.google.com/` placeholder in `index.html` with your actual profile URL.
