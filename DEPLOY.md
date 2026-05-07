# Deploy your portfolio to GitHub Pages

Follow these steps to get your site live at `https://jannatul-mahmud.github.io`.

## Step 1 — Add your résumé and profile photo

1. Find your résumé PDF, rename it to `resume.pdf`, drop it in this folder
2. Find your headshot (the blue-background one with the GitHub icon), rename it to `profile.jpg`, drop it in this folder

⚠️ The filename **must** be exactly `profile.jpg` (lowercase, .jpg extension). If your photo is a `.png` or `.jpeg`, either rename it to `.jpg` (works fine — extensions are just labels) OR open both `index.html` and `about.html` in a text editor and change `src="profile.jpg"` to match your actual filename.

**Photo size tip:** if your photo is huge (5+ MB), shrink it first. Open in Preview → Tools → Adjust Size → set Width to 1200 px → File → Export → JPEG, quality 75%. This makes your site load much faster.

## Step 2 — Open Terminal and go to the folder

```bash
cd ~/Portfolio
```

(Or wherever you saved these files.)

## Step 3 — Initialize Git

```bash
git init
git add .
git commit -m "Initial portfolio commit"
```

## Step 4 — Create a special repo on GitHub

This is the trick that makes GitHub Pages serve your site at `username.github.io`
instead of `username.github.io/some-repo`.

1. Go to **github.com**, log in
2. Click **+** top-right → **New repository**
3. Repository name: **`jannatul-mahmud.github.io`** (use your actual GitHub username,
   followed by exactly `.github.io`)
4. Public
5. **Do NOT** check "Add a README" or anything else
6. Click **Create repository**

## Step 5 — Push your portfolio

```bash
git remote add origin https://github.com/jannatul-mahmud/jannatul-mahmud.github.io.git
git branch -M main
git push -u origin main
```

When asked for password, paste your **Personal Access Token** (the one you used
for the ESP32 repo).

## Step 6 — Turn on GitHub Pages

1. Go to your new repo on GitHub
2. Click **Settings** (top of repo)
3. Click **Pages** (left sidebar)
4. Source: **Deploy from a branch**
5. Branch: **main** / Folder: **/ (root)**
6. Click **Save**

First deploy takes 1-2 minutes.

## Step 7 — Visit your site

```
https://jannatul-mahmud.github.io
```

That's it. Live on the actual web with a real URL you can put on your résumé.

## Updating later

```bash
cd ~/Portfolio
git add .
git commit -m "describe what you changed"
git push
```

GitHub Pages re-deploys automatically within ~1 minute.

## Replacing the demo placeholder

Open `project-traffic-light.html` in a text editor. Find this block:

```html
<div class="video-embed">
  <span>[ Demo video / GIF goes here — replace this block with your media ]</span>
</div>
```

Replace it with:

**For a GIF or photo:**
```html
<div class="video-embed">
  <img src="demo.gif" alt="Traffic light demo">
</div>
```

**For a YouTube video (unlisted is fine):**
```html
<div class="video-embed">
  <iframe src="https://www.youtube.com/embed/YOUR_VIDEO_ID"
          frameborder="0" allowfullscreen></iframe>
</div>
```

**For an MP4 in your folder:**
```html
<div class="video-embed">
  <video src="demo.mp4" controls></video>
</div>
```

Drop the file in the same folder, push, done.
