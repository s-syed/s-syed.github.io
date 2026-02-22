# saifsyed.com — Quarto Website

## How to get this live (one-time setup, ~30 min)

### Step 1 — Install Quarto
Download and install from: https://quarto.org/docs/get-started/
(Pick the installer for your OS — it's a standard .pkg / .exe)

### Step 2 — Create your GitHub repo
1. Go to https://github.com/new
2. Name the repo exactly: `s-syed.github.io`
3. Set it to Public
4. Click "Create repository"

### Step 3 — Put these files in the repo
Option A (easiest): Use GitHub Desktop — drag the contents of this folder into the repo.
Option B: In Terminal, from this folder:
```
git init
git remote add origin https://github.com/s-syed/s-syed.github.io.git
git add .
git commit -m "initial site"
git push -u origin main
```

### Step 4 — Add your photo
Drop your photo into `assets/` and name it `photo.jpg`.
If you want a different filename, edit the `<img src=...>` line in `index.qmd`.

### Step 5 — Publish
In Terminal, from the site folder:
```
quarto publish gh-pages
```
That's it. Your site will be live at https://s-syed.github.io in ~2 minutes.

### Step 6 — Point your domain (optional)
In your domain registrar (wherever saifsyed.com is registered):
- Add a CNAME record: `www` → `s-syed.github.io`
- Or follow GitHub's custom domain guide: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site

---

## How to update the site (day-to-day)

Every update is the same 2-step process:

**1. Edit the file**
- Homepage content: edit `index.qmd`
- Course page: edit `teaching/stat547e.qmd`
- Styles: edit `assets/style.css`

These are plain text files. Open them in any text editor (TextEdit, VS Code, etc).

**2. Republish**
```
quarto publish gh-pages
```

That's the only command you ever need to run.

---

## Common tasks

### Add a new publication
Open `index.qmd`, find the `PUBLICATIONS` section, and copy this block:

```html
<div class="pub-item">
  <div class="pub-title">Your Paper Title</div>
  <div class="pub-authors"><strong>Saifuddin Syed</strong>, Co-author Name</div>
  <div class="pub-venue">Journal Name, Year</div>
  <div class="pub-links">
    <a class="pub-link" href="YOUR_ARXIV_LINK">arXiv</a>
    <a class="pub-link" href="YOUR_PDF_LINK">PDF</a>
  </div>
</div>
```

### Add a news item
Open `index.qmd`, find the `NEWS` section, copy this block:

```html
<div class="news-item">
  <div class="news-date">Month Year</div>
  <div>Your news text here.</div>
</div>
```

### Add lecture slides
Open `teaching/stat547e.qmd`, find the row for that lecture, and change:
```html
<span class="slides-tbd">— upcoming</span>
```
to:
```html
<a class="slides-link" href="PATH_TO_YOUR_PDF">PDF</a>
```
Upload the PDF to the `teaching/` folder first.

### Add a student
Open `index.qmd`, find the `STUDENTS` section, copy this block:

```html
<div class="student-item">
  <div><a href="STUDENT_WEBSITE">Student Name</a></div>
  <div class="student-degree">PhD · UBC Statistics</div>
</div>
```

---

## File structure
```
s-syed.github.io/
├── _quarto.yml          ← site config (nav, theme)
├── index.qmd            ← homepage
├── assets/
│   ├── style.css        ← all styles
│   └── photo.jpg        ← your photo (add this)
├── teaching/
│   └── stat547e.qmd     ← STAT 547E course page
└── uploads/
    └── cv.pdf           ← your CV (add this)
```
