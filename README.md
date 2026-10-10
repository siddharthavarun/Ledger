# Rep Ledger

A fitness tracker you install on your phone from the browser. Log workouts set by set, import workout plans from PDF, and follow weekly insights on training volume and body weight.

## What's in here

| File | What it does |
| --- | --- |
| `index.html` | The whole app |
| `manifest.webmanifest` | Name, icons and colours used when the app is installed |
| `sw.js` | Lets the app open offline. Bump `VERSION` after every change |
| `icons/` | Home-screen and browser icons |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |

## Your data

Everything is saved on the device you use, in the browser's storage. Nothing is uploaded.

- Use **Profile → Your data → Back up** to save a copy, and **Restore** to load it on another phone.
- If you delete the app or clear the browser's site data, data that isn't backed up is gone.

## Publish on GitHub Pages

1. Create an empty repository at <https://github.com/new>, for example `rep-ledger`. Make it **Public**, since free GitHub Pages needs a public repository. Don't add a README or licence.
2. Push this folder, replacing `YOUR-USERNAME`:

   ```bash
   git remote add origin https://github.com/YOUR-USERNAME/rep-ledger.git
   git push -u origin main
   ```

3. In the repository, open **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, then **main** and **/ (root)**, and click **Save**.
4. After a minute or two the app is live at `https://YOUR-USERNAME.github.io/rep-ledger/`.

## Install it on your phone

- **iPhone:** open the link in Safari, tap **Share**, then **Add to Home Screen**.
- **Android:** open the link in Chrome, then tap **Install app** (or ⋮ → **Add to Home screen**).

## Updating the app

1. Edit the files.
2. Change `VERSION` in `sw.js`, for example `rep-ledger-v2`, so installed copies fetch the new version.
3. Commit and push:

   ```bash
   git add -A
   git commit -m "Describe the change"
   git push
   ```

Installed apps update the next time they're opened online. It can take a second launch.

## Try it locally

```bash
python3 -m http.server 8123
```

Then open <http://localhost:8123>.

## PDF plan import

PDFs are read on the device. The reader looks for one exercise per line, for example `Bench press 4 x 8` or `Squat - 3 sets of 10 @ 60kg`, and for day headings like `Day 1`, `Monday` or `Push`. You can edit everything it finds before saving. Scanned PDFs (photos of pages) can't be read.
