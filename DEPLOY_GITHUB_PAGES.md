# GitHub Pages Deployment

## Recommended Settings

- Repository visibility: Public
- Repository name: `Switzerland_2026`
- Pages source: `Deploy from a branch`
- Branch: `main`
- Folder: `/root`

The website URL will be:

```text
https://YOUR_GITHUB_USERNAME.github.io/Switzerland_2026/
```

Use that URL for Klook PubShare, Booking.com Partner, GetYourGuide, and other affiliate applications.

## Public Repository Scope

This public GitHub Pages repository should only publish the website files needed for affiliate review:

- `index.html`
- `confirm.html`
- `daily.html`
- `legal/privacy.html`
- `legal/terms.html`
- `.nojekyll`
- `README.md`

Internal app packaging files, Android signing files, business setup notes, and build artifacts are ignored by `.gitignore`.

## First-Time Terminal Commands

Run these from `/Users/alu/Desktop/Switzerland_2026` after you create an empty GitHub repository named `Switzerland_2026`:

```bash
git init
git branch -M main
git add .
git commit -m "Prepare Switzerland 2026 GitHub Pages site"
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/Switzerland_2026.git
git push -u origin main
```

Then open GitHub repository settings and enable Pages from `main` / `/root`.

## Do Not Upload

The `.gitignore` file excludes Android keystores, signing passwords, local SDK paths, `node_modules`, and build artifacts. Keep these local files backed up securely, but do not publish them:

- `android/app/switzerland2026-upload.jks`
- `android/keystore.properties`
- `android/local.properties`
- `android/app/build/outputs/bundle/release/app-release.aab`
