# ކެންދޫ.ކޮމް — kendhoo.com

A Dhivehi (RTL) news site built with **Jekyll**, hosted free on **GitHub Pages**.
Each article is its own file. Add a file → it appears on the site automatically,
in the hero, the latest list, and its category block.

---

## Folder map

```
kendhoo/
├── index.html          ← homepage (auto-built from articles; don't hand-edit content)
├── _config.yml         ← site settings
├── _layouts/           ← page templates (design lives here)
│   ├── default.html    ←   header, nav, footer, all styles + scripts
│   └── post.html       ←   the single-article page
├── _includes/
│   └── date.html       ←   Dhivehi date formatter
├── _posts/             ← YOUR ARTICLES GO HERE ★
│   └── 2026-08-04-kendhoo-bandaru.md   (+ more samples)
├── 404.html
├── CNAME               ← kendhoo.com
└── .gitignore
```

You only ever touch **`_posts/`** to publish. Everything else is the machinery.

---

## ★ How to publish a new article (on GitHub, no tools)

1. Open your repo → click the **`_posts`** folder.
2. Click **Add file → Create new file**.
3. **Name it** using this exact pattern — date, then a short English slug, then `.md`:
   ```
   2026-08-10-kendhoo-council-meeting.md
   ```
   (The date controls ordering; the slug becomes the web address. Use only
   lowercase letters, numbers and hyphens in the slug — no spaces, no Thaana.)
4. **Paste this template** and fill it in:
   ```
   ---
   layout: post
   title: "ސުރުޚީ މިތާ ލިޔޭ"
   category: "ރާއްޖެ"
   date: 2026-08-10 09:00:00 +0500
   image: "https://picsum.photos/seed/anything/1200/675"
   excerpt: "ކުރު ޚުލާޞާއެއް މިތާ ލިޔޭ."
   featured: false
   ---

   ފުރަތަމަ ޕެރެގްރާފް މިތާ ލިޔޭ.

   ## ސެކްޝަން ސުރުޚީ

   އިތުރު ލިޔުން މިތާ ލިޔޭ.
   ```
5. Scroll down, click **Commit new file**.

That's it. Within ~1 minute GitHub rebuilds and the article is live at
`kendhoo.com/news/kendhoo-council-meeting/`.

### The fields explained
| Field       | What it does                                                          |
| ----------- | --------------------------------------------------------------------- |
| `title`     | The headline (Thaana). Keep it inside the quotes.                     |
| `category`  | Which block it shows in. Use one of the categories listed below.      |
| `date`      | `YYYY-MM-DD HH:MM:SS +0500` — `+0500` is Maldives time. Newest first. |
| `image`     | Cover image URL. Replace picsum links with your real photo URLs.      |
| `excerpt`   | Short summary shown under the headline.                               |
| `featured`  | Set **one** article to `true` to make it the big hero story. Rest `false`. |

**Categories** (type one, exactly): `ރާއްޖެ`, `ފަތުރުވެރިކަން`, `ކުޅިވަރު`,
`ވިޔަފާރި`, `ދުނިޔެ`, `މުނިފޫހިފިލުވުން`, `ރިޕޯޓް`.

### Editing or deleting
- **Edit:** open the file in `_posts/`, click the ✏️ pencil, change, commit.
- **Delete:** open the file, click the 🗑️ trash icon, commit.

---

## Putting this on your repo the first time

Your repo currently has the old single-file version. Replace it with this
structure. Easiest is the command line from inside this folder:

```bash
git clone https://github.com/Baloo333/kendhoo.git
# copy all these files into that folder (including _posts, _layouts, _includes)
cd kendhoo
git add .
git commit -m "Convert site to Jekyll with article files"
git push
```

Or via the website: repo → **Add file → Upload files**, then drag in the
top-level items **including the `_posts`, `_layouts`, and `_includes` folders**
(GitHub keeps the folder structure). Commit. It overwrites the old `index.html`
and adds the rest.

> After pushing, check the **Actions** tab. A green check = built and live.
> A red X = a typo in an article's front matter (usually a missing quote).

---

## Later: add the form editor (Decap CMS)

When you want to stop editing files by hand, Decap CMS adds an admin page at
`kendhoo.com/admin` with a proper form (title, category, image upload, body).
It reads and writes these **same `_posts` files**, so nothing here changes —
it just sits on top. It needs a one-time login setup via a small Cloudflare
Worker (you already use Cloudflare). Ask when you're ready and it can be wired in.

---

## Local preview (optional)

```bash
gem install jekyll bundler
jekyll serve
# open http://localhost:4000
```
