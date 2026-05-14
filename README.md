# M. Conradi — static press site

Single-page artist / press kit: plain HTML + CSS (one small script for the copyright year). Replace placeholders in `index.html` as you go; add assets under `images/`.

## Preview locally

Open `index.html` in your browser, or from this folder run a tiny static server (optional):

```bash
python3 -m http.server 8080
```

Then visit `http://localhost:8080`.

## Swap embeds and links

| What | Where |
|------|--------|
| **YouTube** | Section “Video”: in the `iframe`, replace the id in `…/embed/VIDEO_ID` with the id from your watch URL. |
| **Spotify** | Spotify app/web → Share → **Embed** → copy the `<iframe>` → paste inside the Spotify card in `index.html` (remove the gray placeholder `div` if you keep only the iframe). |
| **SoundCloud** | Track or playlist → Share → **Embed** → copy `<iframe>` → paste into the SoundCloud card. |
| **Bandcamp** | “Download songs” uses the official embed iframe; tweak `src` (album id, colors, `tracklist`, etc.) in `index.html`. The “More releases” link goes to your full discography. |
| **Hero + gallery** | Add optimized images to `images/` and update `src` (and `alt`) on `<img>` tags. See `images/README.md`. |
| **Email & social** | Footer and “Contact”: change `mailto:` and the `href="#"` links to real URLs. |

Bio text in the hero is taken from your existing `Media Kit/M.Conradi - English Bio.rtf`; edit the paragraphs in `index.html` anytime.

## Deploy on GitHub Pages

1. Push this repository to GitHub.
2. Repo → **Settings** → **Pages**.
3. **Build and deployment**: Source = **Deploy from a branch**, Branch = `main` (or `master`), folder = **`/ (root)`** if `index.html` is at the repository root.
4. Save. After a minute or two, the site will be at `https://<username>.github.io/<repo>/` (unless it is a user/org site named `<username>.github.io`, in which case the URL is `https://<username>.github.io/`).

No build step is required. If you ever add folders that start with underscores and GitHub mis-detects Jekyll, add an empty `.nojekyll` file at the repo root (not needed for this default layout).

## Custom domain (mconradi.com) — later

Domain is on Namecheap. Once you are ready:

1. In GitHub Pages settings, set **Custom domain** to `mconradi.com` and enable **Enforce HTTPS** after DNS propagates.
2. At Namecheap (or DNS host), add the records GitHub documents for your apex (`@`) and `www` (typically `A`/`AAAA` to GitHub’s IPs or a `CNAME` for `www` to `<user>.github.io`). Exact values: [GitHub Pages custom domain](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

This step is optional for the first static build; the site works on the `github.io` URL immediately.
