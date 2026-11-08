# Daily stuff – offline app

Works with no internet and no Claude once installed. Your data lives on each device.

## Put it online once (free, 5 min) – GitHub Pages
1. github.com → New repository → name it `daily-stuff` → Public → Create.
2. "uploading an existing file" → drag in everything from this folder → Commit.
3. Settings → Pages → Source: Deploy from a branch → Branch: main, / (root) → Save.
4. Wait ~1 min. Your app is at https://<your-username>.github.io/daily-stuff/

## Install it
- iPhone: open the link in **Safari** → Share → **Add to Home Screen**.
- Android: open in **Chrome** → ⋮ → **Install app** / Add to Home screen.
- Laptop: open in Chrome/Edge → install icon in the address bar.
Open it once while online. After that it works offline.

## Move your data in
In the Claude version: Dashboard → Download backup.
In this app: Dashboard → Restore from file → pick that file.

## Phone ⇄ laptop
There's no server, so devices don't sync by themselves. Use Download backup on one
and Restore from file on the other. Do a backup every week or so anyway.

## Updating
Change index.html, then bump VERSION in sw.js (v1 → v2) and upload both.
