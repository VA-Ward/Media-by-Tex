# Media by Tex — Static Website

This is the whole website as **static files** — no server, nothing to keep running, nothing to pay for. It's hosted free on GitHub Pages, forever. The photo gallery lives in a simple file (`gallery.json`) that the site reads.

**What's in here**

- `index.html` — the website.
- `gallery.json` — the list of gallery photos (titles, categories, captions, order).
- `images/` — the photo files.
- `admin.html` — an optional point-and-click tool for managing photos (see below).
- `README.md` — this guide.

---

## 1. Put it online (one-time, ~10 minutes)

1. Create a free account at [github.com](https://github.com) if you don't have one.
2. Click **+ → New repository**. Give it a name, keep it **Public**, and create it.
3. On the new repo page, click **uploading an existing file** (or **Add file → Upload files**). Drag in **everything from this folder** — `index.html`, `gallery.json`, `admin.html`, and the **`images`** folder — then **Commit changes**.
4. Go to **Settings → Pages**. Under *Build and deployment*, set **Source** to *Deploy from a branch*, **Branch** to `main`, folder `/ (root)`, and **Save**.
5. Wait a minute, refresh, and your live address appears at the top of that Pages page (something like `https://your-name.github.io/your-repo/`).

That's the site live. Nothing else runs.

---

## 2. Managing your photos — two ways

### Way A — The admin tool (point and click)

Open **`admin.html`** on your live site (e.g. `https://your-name.github.io/your-repo/admin.html`). It lets you add, edit, reorder, hide, and delete photos — and manage your Instagram feed — then saves the changes back into your repo for you.

**Signing in.** The admin is password-protected. The default login is username **`tex`**, password **`mediabytex`** — please change it: on the sign-in screen open *"Set or change the password"*, type a new password, click **Generate**, and follow the one-line instruction it gives you. (This login keeps casual visitors out; the real lock on saving is still your GitHub token below, so nothing can be changed without it.)

After signing in, the first time it asks for two things:

- **Your repository address** — paste your repo's GitHub URL.
- **An access token** — a one-time key so it can save changes. The tool has a step-by-step "How do I get a token?" link built in. In short: create a **fine-grained token** at GitHub, give it access to **only your website repo**, with **Contents: Read and write** permission, and paste it in.

Your token is kept only in your browser tab — it's never saved into the site, so it's safe to have `admin.html` on your live address. You can revoke the token on GitHub anytime. After you click **Save to GitHub**, changes appear on the live site within about a minute.

### Way B — Edit the file directly (no token)

If you'd rather not bother with a token, edit `gallery.json` on GitHub. Each photo is one block:

```json
{ "id": "race-ready", "title": "Race Ready", "category": "brands",
  "caption": "Trail build", "size": "wide",
  "image": "images/BRANDS_Race_Ready.jpg", "published": true }
```

- **title** — the name shown on the photo.
- **category** — `nature`, `athletes`, or `brands` (drives the filter buttons).
- **caption** — the small line under the title.
- **size** — `wide` for a feature shot, `tall` for a standard one.
- **image** — the file in your `images` folder. To add a new photo, upload the file to the `images` folder first (Add file → Upload files), then point `image` at it.
- **published** — `true` to show it, `false` to hide it without deleting.

The order of the blocks is the order they appear on the site. Edit on GitHub (pencil icon), commit, and the site updates within a minute.

---

## 3. Enquiries

A static site can't run an inbox, so the contact form opens the visitor's email app with their message ready to send to you. To change the address it sends to, update `hello@mediabytex.com.au` in `index.html`.

If you'd prefer messages to arrive automatically without the visitor's email app opening, a free form service (such as Formspree or Web3Forms) can do that on a static site — just ask and I'll wire it in.

---

## 4. Instagram feed

The page has an **On Instagram** section (between Projects and Contact) for a live feed of @media_by_tex's posts, powered by SociableKIT (free forever). Until you connect it, that section shows a small placeholder note — visitors won't see anything broken. You manage it from the **admin panel** (no editing code), in the *Instagram feed* box below the photos.

To switch it on (about two minutes, no cost):

1. Sign up at [sociablekit.com](https://www.sociablekit.com).
2. Choose the **Instagram Profile** widget.
3. Enter the username `media_by_tex` and pick a layout and colours (a dark/grid layout suits the site).
4. Click **Embed on website** and copy the code it gives you.
5. In the admin panel, paste that code into the **Instagram feed** box (use **Preview** to check it), then click **Save to GitHub**.

To remove the feed later, just clear that box and save. A couple of notes: new posts appear on the site after SociableKIT's sync runs (every so often, not instantly — faster sync is a paid option), and this shows a live feed of your latest posts, separate from the curated Projects gallery. If you'd like the feed in the top menu too, just ask.

---

## Good to know

- **Changes go live about a minute after saving** — GitHub rebuilds the site each time.
- **Deleting a photo** removes it from the gallery; the image file stays in the `images` folder (harmless — you can delete it there if you want a tidy-up).
- **Hero & portrait:** the nine gallery photos are real. The big banner image at the top and the portrait in *Meet Tex* are still placeholders — replace them by adding the files and updating their two `src="..."` links in `index.html`.
- **Keep your token private**, and revoke it on GitHub if it's ever exposed.
