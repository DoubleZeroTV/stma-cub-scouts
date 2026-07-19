# STMA Cub Scouts — Website

A free, fast, static website for **stmacubscouts.com**. No monthly hosting fees — it runs on GitHub Pages (free) and you keep your GoDaddy domain (you only pay the yearly domain renewal).

The design, colors (`#0c6acf`), and copy are modeled on the Pack 3547 site so it feels familiar, but this version is an **umbrella** for all the STMA packs, with a page for each pack.

---

## What's in this folder

| File | What it is |
|------|-----------|
| `index.html` | The main home page (hero, Find Your Pack, Why Cub Scouts, Ranks, FAQ, Contact). |
| `pack-3547.html` | A finished example pack page, filled in with Pack 3547's real info. |
| `pack-template.html` | A blank pack page — copy it to add a new pack. |
| `styles.css` | The shared look & feel for every page. Edit once, changes everywhere. |
| `images/` | Put your photos here (see "Adding photos" below). |

To preview it on your computer, just double-click `index.html` — it opens in your browser.

---

## Put it online free (GitHub Pages)

1. **Create a free account** at [github.com](https://github.com).
2. Click **New repository**. Name it anything (e.g. `stma-cub-scouts`). Set it to **Public**. Click **Create**.
3. On the new repo page, click **uploading an existing file**, then drag in **all the files from this folder** (including the `images` folder). Click **Commit changes**.
4. Go to **Settings → Pages**. Under "Build and deployment", set **Source: Deploy from a branch**, **Branch: main**, folder **/ (root)**. Click **Save**.
5. Wait ~1 minute, refresh, and GitHub shows your live URL: `https://YOUR-USERNAME.github.io/stma-cub-scouts/`.

Your site is now live and free. 🎉

---

## Connect your GoDaddy domain (stmacubscouts.com)

You keep the domain at GoDaddy but point it at GitHub's free hosting.

1. In your GitHub repo: **Settings → Pages → Custom domain**, type `stmacubscouts.com`, click **Save**. (This adds a `CNAME` file to the repo — leave it there.)
2. Log in to **GoDaddy → your domain → DNS**. Add these records:

   **Four A records** (host `@`) pointing to GitHub's IP addresses:
   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```
   **One CNAME record**: host `www` → value `YOUR-USERNAME.github.io`

3. Back in GitHub Pages settings, check **Enforce HTTPS** once it becomes available (may take an hour or so). That gives you free https:// security.

DNS changes can take a few minutes to a few hours to take effect. After that, `stmacubscouts.com` loads your free site.

> Want both `stmacubscouts.com` and `stmascouts.com`? Point the second domain's DNS the same way, or set it to forward to the first (GoDaddy → domain → Forwarding).

---

## Add a new pack (takes 5 minutes)

1. **Duplicate** `pack-template.html` and rename it, e.g. `pack-1234.html`.
2. Open it in any text editor and replace the CAPITALIZED placeholders:
   - `PACK_NUMBER`, `PACK_TOWN`, `MEETING_TIME`, `MEETING_LOCATION`
   - `REGISTER_LINK` (that pack's my.scouting.org registration URL)
   - `PACK_EMAIL` and the three About paragraphs
3. Open `index.html`, find the **Find Your Pack** section, copy one of the `<div class="card">…</div>` blocks, and update its name, town, description, and the two links (`pack page →` should point to your new file; `Register →` to the registration link).
4. Re-upload the changed files to GitHub (drag them in and commit). Live in ~1 minute.

---

## Your photos — already matched up ⭐

The pages are **already wired** to your Dropbox photos. I couldn't copy the image files into this folder automatically (the tool can't reach Dropbox's file servers), so there's one easy step left for you:

**Copy every file from your Dropbox "STMA scouts images" folder into this site's `images/` folder — keep the filenames exactly as they are.** The moment they're in there, all the photos appear. No renaming needed.

Here's where each photo I used lands on the site:

| Photo (Dropbox filename) | Where it shows up |
|---|---|
| `Cub_Scouting_1920x1080 (1).png` | Home page hero background |
| `AT4A2927-edited-photo-CSBC-small_compressed.webp` | Home "Welcome, Families!" photo |
| `062A7291_photo_CSBC-small_compressed.jpeg` | Pack 3547 card on the home page |
| `gmf_Climbing-Activity_800x640 (1).jpg` | "Adventure Awaits" → Outdoor Skills |
| `cheerful-multicultural-kids-...webp` | "Adventure Awaits" → STEM Activities |
| `Parents-New-to-Scouting-...webp` | "Adventure Awaits" → Life Skills |
| `gmf_Archery-Activity_800x640 (1).jpg` | "Life in the Pack" photo strip |
| `IMG_0717_compressed.webp` | Photo strip + Pack 3547 About |
| `gmf_BouncePillow-Activity_800x640 (1).jpg` | Photo strip + Pack 3547 About |
| `IMG_9846_compressed.webp` | Photo strip + Pack 3547 About |
| `Cub scouts pack 547-Logo and word mark (1).png` | Pack 3547 page header (logo) |
| `lion-scout-slide.png` | Pack 3547 → Lion rank |
| `Tiger-cub-5b3950b (1).jpg` | Pack 3547 → Tiger rank |
| `Wolf (1).jpg` | Pack 3547 → Wolf rank |
| `bear.jpg` | Pack 3547 → Bear rank |
| `Webelos.jpg` | Pack 3547 → Webelos rank |

I matched these by filename since I couldn't open the pictures — if any photo would look better somewhere else, just tell me and I'll swap it (or open the `.html` file and change the filename in the `src="images/..."` tag).

**Swapping or adding more photos:** drop the file into `images/`, then point an `<img>` at it, e.g.:
```html
<img src="images/my-photo.jpg" alt="Pack 3547 at the fall campout">
```
Keep files under ~500 KB so pages load fast — shrink them free at [squoosh.app](https://squoosh.app).

---

## Changing colors or text

- **Colors:** open `styles.css` and edit the values at the very top (`--blue`, `--gold`, etc.). Every page updates at once.
- **Text:** open any `.html` file and edit the words between the tags. Save, re-upload, done.

Questions on any step — just ask and I'll walk you through it.
