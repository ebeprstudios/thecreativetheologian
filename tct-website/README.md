# the creative theologian
### arts · faith · story

A curated platform for faith-based storytelling, interviews, and creative showcases.  
Built as a static HTML site — fast, portable, and deployable anywhere.

---

## Folder Structure

```
tct-website/
├── index.html                  ← Main homepage
├── README.md                   ← You are here
├── .gitignore
│
├── posts/                      ← Blog posts & features
│   ├── template.html           ← Copy this to create new posts
│   └── [post-slug].html        ← One file per post
│
├── notes/                      ← Sermon notes
│   ├── template.html           ← Copy this to create new notes
│   └── [note-slug].html        ← One file per note
│
├── pages/                      ← Static pages (About, Submit, etc.)
│
└── assets/
    ├── images/                 ← Drop all photos here
    ├── videos/                 ← Drop video files here (or use Cloudinary)
    └── fonts/                  ← Custom fonts if added locally
```

---

## Deploying to Vercel via GitHub

### First Time Setup

**1. Push to GitHub**
```bash
cd tct-website
git init
git add .
git commit -m "initial: CTN website launch"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/tct-website.git
git push -u origin main
```

**2. Deploy on Vercel**
1. Go to [vercel.com](https://vercel.com) → log in with GitHub
2. Click **"Add New Project"**
3. Select your `tct-website` repository
4. Leave all settings as default — Vercel auto-detects static HTML
5. Click **Deploy**

Your site will be live at `tct-website.vercel.app` in ~30 seconds.

---

### Connect Your Custom Domain

1. In Vercel → your project → **Settings → Domains**
2. Add: `thecreativetheologian.com` and `www.thecreativetheologian.com`
3. Vercel shows you DNS records — add them in your domain registrar:

| Type  | Name | Value                    |
|-------|------|--------------------------|
| A     | @    | 76.76.21.21              |
| CNAME | www  | cns1.vercel-dns.com      |

SSL/HTTPS auto-provisions. No extra steps.

---

### Updating the Site (Ongoing)

Every future update is just:
```bash
git add .
git commit -m "update: [what you changed]"
git push
```
Vercel auto-deploys in ~25 seconds. No dashboard interaction needed.

---

## Adding a New Blog Post

1. Duplicate `posts/template.html`
2. Rename it to match the post topic: `posts/from-graveyards-to-glory.html`
3. Edit the template — replace the placeholder content:
   - Update `<title>` and meta tags
   - Replace the post title, date, category
   - Write your content in the `<article>` section
   - Add images using `<img src="../assets/images/YOUR-IMAGE.jpg">`
4. Link to it from `index.html` by updating the blog card `href`
5. Push to GitHub — Vercel deploys automatically

---

## Adding a New Sermon Note

1. Duplicate `notes/template.html`
2. Rename it: `notes/weight-of-glory.html`
3. Edit:
   - Update note number, title, scripture reference
   - Write your content in the note body
   - Add a cover image if desired
4. Link from `index.html` sermon card `href`
5. Push and deploy

---

## Adding Images

Drop images into `assets/images/` and reference them in HTML like:
```html
<!-- From index.html -->
<img src="assets/images/mia-crews-feature.jpg" alt="Mia Crews">

<!-- From a post file (one folder deep) -->
<img src="../assets/images/mia-crews-feature.jpg" alt="Mia Crews">
```

**Recommended image sizes:**
- Hero / featured: 1600×900px or 1600×1000px
- Blog card thumbnails: 800×500px
- Sermon note cover: 800×450px
- Portrait / reel cards: 600×750px

**For video** — use Cloudinary (already configured in your workflow) and paste the URL directly into the `<video src="">` tag or the upload handler.

---

## Brand Quick Reference

| Token       | Value     | Usage                        |
|-------------|-----------|------------------------------|
| `--black`   | `#0A0A0A` | Page background              |
| `--surface` | `#111111` | Section backgrounds          |
| `--card`    | `#161616` | Card backgrounds             |
| `--cream`   | `#E8DDD0` | Primary text                 |
| `--muted`   | `#9E8E7E` | Body copy, secondary text    |
| `--taupe`   | `#7A6B5D` | Labels, metadata             |
| `--linen`   | `#C4B49A` | Accent, tags, hover elements |
| `--border`  | `#272220` | Borders, dividers            |

Fonts: **Cormorant Garamond** (display) · **Jost** (body) · **DM Mono** (labels/metadata)

---

## Phase Two (When Ready)

- **Cloudinary** — image & video CDN (already in your THCO workflow)
- **Sanity CMS** — add/edit posts without touching code
- **Vercel Analytics** — free traffic dashboard, enable in Vercel settings
