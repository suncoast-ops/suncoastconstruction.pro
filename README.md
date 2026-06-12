# Suncoast Construction Inc. — Website

Single-file website for Suncoast Construction Inc. — no dependencies, no CDNs, no build step. The logo is embedded directly as base64 inside `index.html`, so the entire site is self-contained in one file.

## Files

| File | Purpose |
|---|---|
| `index.html` | Complete website — HTML + CSS + JS, logo embedded |
| `CNAME` | Tells GitHub Pages to serve from `suncoastconstruction.pro` |
| `README.md` | This file |

---

## Deploying to GitHub Pages with Custom Domain

### Step 1 — Create a GitHub Repository

1. Go to [github.com](https://github.com) and sign in.
2. Click **+** → **New repository**.
3. Name it anything (e.g. `suncoast-site`). Set it to **Public**.
4. Click **Create repository**. Leave it empty (no README).

### Step 2 — Upload the Files

**Option A — Browser drag-and-drop (easiest):**
1. Open your new repository.
2. Click **Add file** → **Upload files**.
3. Drag `index.html` and `CNAME` into the upload area.
4. Click **Commit changes**.

**Option B — Git CLI:**
```bash
git init
git add index.html CNAME
git commit -m "Launch Suncoast Construction website"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages

1. In your repository → **Settings** → **Pages** (left sidebar).
2. Under **Source**: select **Deploy from a branch**.
3. Branch: **main**, folder: **/ (root)**.
4. Click **Save**.

GitHub will show: *"Your site is ready to be published."*

### Step 4 — Point Your Domain to GitHub Pages

Log in to your domain registrar (wherever you bought `suncoastconstruction.pro`) and set these **DNS records**:

#### A Records (point apex domain to GitHub)
| Type | Host | Value |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |

#### CNAME Record (point www subdomain)
| Type | Host | Value |
|---|---|---|
| CNAME | www | YOUR-USERNAME.github.io |

> DNS changes can take 10 minutes to 48 hours to propagate globally.

### Step 5 — Enable HTTPS (free SSL)

1. Back in GitHub repo → **Settings** → **Pages**.
2. In the **Custom domain** box, enter: `suncoastconstruction.pro`
3. Click **Save**.
4. Wait ~10 minutes, then check **Enforce HTTPS** and save.

Your site will be live at **https://suncoastconstruction.pro**

---

## Adding a Contact Form Backend (Optional)

The form currently shows a success message without sending email. To wire it up to a real email inbox:

### Option — Formspree (free tier, no backend code needed)
1. Create a free account at [formspree.io](https://formspree.io).
2. Create a new form → copy your endpoint (e.g. `https://formspree.io/f/xabc1234`).
3. In `index.html`, find the `submitForm()` function and replace it with a `fetch` POST to your Formspree endpoint.

---

## Updating Contact Info

Everything is in `index.html`. Search for:
- **Phone:** `4079159027` (appears in several `href="tel:"` and display links)
- **Address:** `Sarasota, FL 34232`
- **Domain:** `suncoastconstruction.pro`

---

## Color Reference (from logo)

| Token | Hex | Use |
|---|---|---|
| Navy | `#1B2A5C` | Primary backgrounds, nav |
| Orange | `#F47920` | CTAs, accents, hover states |
| Amber | `#F5A623` | Secondary accent, stats |
| Blue | `#4A9FD4` | Tags, tertiary elements |
| Off-white | `#F7F8FA` | Section backgrounds |

---

© 2025 Suncoast Construction Inc.
