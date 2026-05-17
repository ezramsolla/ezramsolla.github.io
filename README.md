# Academic Website

A clean, static academic personal website inspired by [Jon Barron](https://jonbarron.info/) and [Oliver Philcox](https://oliverphilcox.github.io/). Pure HTML/CSS — no build tools, no frameworks, deploys to GitHub Pages instantly.

## Structure

```
.
├── index.html                  ← About / home (with Selected Publications)
├── assets/
│   ├── css/style.css           ← All shared styles + dark/light mode
│   └── theme.js                ← Dark/light toggle (persists via localStorage)
├── research/
│   └── index.html
├── blog/
│   ├── index.html              ← Post listing
│   └── post-template.html      ← Copy this for each new post
└── cv/
    ├── index.html
    └── CV.pdf                  ← Drop your PDF CV here
```

## Deploy to GitHub Pages

### Option A — yourname.github.io (recommended)

1. Create a repo named `<username>.github.io`
2. Push all files to the `main` branch:
   ```bash
   git clone https://github.com/<username>/<username>.github.io.git
   # copy all files in
   git add .
   git commit -m "Initial site"
   git push
   ```
3. Live at `https://<username>.github.io` within ~60 seconds. No settings needed.

### Option B — project site

1. Create any repo, push files to `main`
2. Go to **Settings → Pages → Source → main / root**
3. Live at `https://<username>.github.io/<repo-name>`
   > Update all relative paths to include `/<repo-name>/` prefix, or add `<base href="/repo-name/">` in each `<head>`.

## Dark / Light Mode

The toggle button in the top-right of the nav switches modes and saves your preference to `localStorage`. On first visit, it respects the visitor's OS setting (`prefers-color-scheme`).

## Customisation Checklist

- [ ] **index.html** — name, title, institution, bio text
- [ ] **index.html** — social links (email, LinkedIn, GitHub, InspireHEP)
- [ ] **index.html** — Selected Publications (add your papers with arXiv/DOI links)
- [ ] **research/index.html** — research areas and figures
- [ ] **blog/index.html** — add post entries; copy `post-template.html` for each post
- [ ] **cv/index.html** — degrees, positions, awards, teaching, service
- [ ] **cv/CV.pdf** — drop your actual PDF here
- [ ] All `<title>` tags — replace "Your Name"
- [ ] Footer — replace name

## Adding Your Photo

Put `photo.jpg` in `assets/img/` and replace the `<div class="photo-placeholder">` in `index.html` with:

```html
<img src="assets/img/photo.jpg" alt="Your Name"
     style="width:180px;height:180px;border-radius:50%;object-fit:cover;border:3px solid var(--border);" />
```

## Adding a Blog Post

1. Copy `blog/post-template.html` → `blog/my-post-title.html`
2. Edit the title, date, tags, and body content
3. Add a link to it in `blog/index.html`

## Custom Domain

Add a `CNAME` file to the repo root:
```
yourdomain.com
```
Then configure your DNS to point to GitHub Pages ([docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)).
