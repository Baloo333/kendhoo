# ކެންދޫ.ކޮމް — kendhoo.com

A responsive, right-to-left (RTL) Dhivehi news website. Static site — pure
HTML/CSS/JS, no build step, hosted free on **GitHub Pages**.

## Files

| File          | Purpose                                             |
| ------------- | --------------------------------------------------- |
| `index.html`  | The homepage (this is what GitHub Pages serves).    |
| `404.html`    | Shown when a page isn't found.                      |
| `CNAME`       | Tells GitHub Pages to serve at `kendhoo.com`.       |
| `.gitignore`  | Keeps editor/OS junk out of the repo.               |
| `README.md`   | This file.                                          |

> **Don't want the custom domain yet?** Delete `CNAME` and the site will live at
> `https://<your-username>.github.io/<repo-name>/` instead.

---

## Deploy — Option A: GitHub website (no tools to install)

1. Go to <https://github.com/new> and create a repository.
   - Name it `kendhoo` (or anything). Keep it **Public**.
2. On the new repo page, click **uploading an existing file**.
3. Drag **all the files in this folder** (`index.html`, `404.html`, `CNAME`,
   `.gitignore`, `README.md`) into the upload area, then **Commit changes**.
4. Go to **Settings → Pages**.
5. Under **Build and deployment → Source**, choose **Deploy from a branch**.
   Set branch to **main** and folder to **/(root)**, then **Save**.
6. Wait ~1 minute. Your site goes live. GitHub shows the URL at the top of the
   Pages settings.

## Deploy — Option B: Git command line

Run these from inside this folder (replace `YOUR-USERNAME`):

```bash
git init
git add .
git commit -m "Launch kendhoo.com"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/kendhoo.git
git push -u origin main
```

Then do steps 4–6 from Option A to switch Pages on.

---

## Custom domain: kendhoo.com

Because a `CNAME` file is included, GitHub Pages will want to serve the site at
`kendhoo.com`. To make that work, add these records at your **domain
registrar's DNS** settings:

**Apex domain (kendhoo.com)** — four `A` records pointing to GitHub:

```
A   @   185.199.108.153
A   @   185.199.109.153
A   @   185.199.110.153
A   @   185.199.111.153
```

**www subdomain (optional but recommended):**

```
CNAME   www   YOUR-USERNAME.github.io
```

Then in **Settings → Pages → Custom domain**, enter `kendhoo.com`, save, and
tick **Enforce HTTPS** once the certificate is issued (can take up to an hour).

DNS changes can take anywhere from a few minutes to 24 hours to take effect.

---

## Editing later

Everything is inside `index.html` — the CSS is in the `<style>` block and the
JS in the `<script>` block at the bottom. Replace the `picsum.photos` image
URLs with your own photos and swap the placeholder Dhivehi headlines with real
articles. Commit and push again (or re-upload) and Pages updates automatically.
