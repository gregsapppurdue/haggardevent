# Push to GitHub & turn on Pages — pick whichever path is easiest

Your repo already exists and is empty:
**https://github.com/gregsapppurdue/haggardevent**

I couldn't push from my sandbox because I don't have your GitHub credentials. Pick one of the three paths below — all three end up at the same result.

---

## Option A — Drag & drop in the browser (30 seconds, no terminal)

1. Go to **https://github.com/gregsapppurdue/haggardevent**
2. Click **"uploading an existing file"** (the link in the empty-repo instructions), or **Add file → Upload files**.
3. Drag `index.html` and `README.md` from this folder into the browser window.
4. Scroll down, leave "Commit directly to the `main` branch" selected, click **Commit changes**.
5. Then see **"Turn on GitHub Pages"** below.

That's it — you don't need the `.bundle` file for this path.

---

## Option B — Terminal, using the bundle (preserves the commit I prepared)

Open Terminal, then:

```bash
cd ~/Desktop                # or wherever you want the working copy
cp "/path/to/github-push/haggardevent.bundle" .
git clone haggardevent.bundle haggardevent
cd haggardevent
git remote set-url origin https://github.com/gregsapppurdue/haggardevent.git
git push -u origin main
```

The first `git push` will prompt for your GitHub username and a **Personal Access Token** (GitHub no longer accepts your account password for git push). If you don't have a PAT handy: GitHub → Settings (top-right) → Developer settings → Personal access tokens → Tokens (classic) → Generate new token → tick **`repo`** scope → copy the token and paste it as your password.

Then see **"Turn on GitHub Pages"** below.

> Tip: find the folder path by right-clicking `github-push` in Finder and picking **"Copy as Pathname"**, then paste it in place of `"/path/to/github-push/..."` above.

---

## Option C — Terminal, starting from scratch

If you'd rather skip the bundle and just publish the two files:

```bash
cd "/path/to/github-push"
rm -rf .git          # only if a stale .git subfolder is present
git init -b main
git config user.email "g.sapp.artisan@gmail.com"
git config user.name  "Gregory Sapp"
git add index.html README.md
git commit -m "Initial commit: meet-and-greet invitation and RSVP page"
git remote add origin https://github.com/gregsapppurdue/haggardevent.git
git push -u origin main
```

Same PAT prompt as Option B.

---

## Turn on GitHub Pages (one-time, ~10 seconds)

Once the files are in the repo:

1. On the repo page, click **Settings** (top-right tabs).
2. In the left sidebar, click **Pages**.
3. Under **Build and deployment**:
   - **Source:** *Deploy from a branch*
   - **Branch:** `main`  /  `/ (root)`  → click **Save**
4. Wait ~30–60 seconds, refresh the Pages settings page. You'll see:
   **"Your site is live at https://gregsapppurdue.github.io/haggardevent/"**

That's your public RSVP link. Share it with guests.

---

## Verifying it works end-to-end

Once the Pages URL is live:

1. Open `https://gregsapppurdue.github.io/haggardevent/` in a private/incognito window.
2. Submit a test RSVP.
3. Confirm a new row appears in the RSVP Haggard Event sheet.
4. Confirm the notification email arrives at g.sapp.artisan@gmail.com.

If step 3 fails, the Apps Script Web App URL may need re-deploying (Apps Script editor → Deploy → Manage deployments). The site itself is working whenever the "You're on the list!" banner appears.

---

## Files in this folder

- **`index.html`** — the invitation page (identical to `meet-craig-rsvp.html` in the parent folder, just renamed for GitHub Pages).
- **`README.md`** — the repo README, seen on the GitHub repo page.
- **`haggardevent.bundle`** — portable git bundle for Option B. Safe to delete once the push is done.
- **`PUSH-INSTRUCTIONS.md`** — this file. Also safe to delete; no need to push it.
