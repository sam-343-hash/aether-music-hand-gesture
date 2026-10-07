# GitHub Guide (step by step)

## Option A: Upload through the website (no Git needed)
1. Sign in at github.com and click **+ → New repository**.
2. Name it `aether-gesture-music`, choose **Public**, and click **Create repository**.
3. Click **uploading an existing file**.
4. Drag in the files (not the folder): `index.html`, `README.md`, `LICENSE`, `CONTRIBUTING.md`, `.gitignore`, `GITHUB_GUIDE.md`.
5. Click **Commit changes**.

## Option B: Use the Terminal (Mac/Linux)
```bash
cd ~/Downloads/aether-gesture-music   # your real folder path
git init
git add .
git commit -m "Initial commit: Aether gesture music"
git branch -M main
git remote add origin https://github.com/<your-username>/aether-gesture-music.git
git push -u origin main
```
Create the empty repo on github.com first (without adding a README there).

## Turn on the live demo (GitHub Pages)
1. Repo **Settings → Pages**.
2. **Deploy from a branch → main → / (root) → Save**.
3. Wait about a minute, then open `https://<your-username>.github.io/aether-gesture-music/`.

## Finishing touches
- Add the live link to the top of the README.
- In the repo sidebar, click the gear next to **About** and add a description plus topics such as `music`, `hand-tracking`, `mediapipe`, `web-audio`.
- Add a screenshot or GIF to the README (upload it to the repo and link with `![demo](demo.gif)`).

## Updating later
```bash
git add .
git commit -m "Describe your change"
git push
```
