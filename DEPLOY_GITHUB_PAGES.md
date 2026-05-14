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

- `index.html`（旅遊行程主頁，已移除私人商業內容）
- `daily.html`（每日詳細行程）
- `legal/privacy.html`
- `legal/terms.html`
- `.nojekyll`
- `README.md`

### 絕對不可上線（已被 `.gitignore` 排除）

- `private/`（私人營運資料夾，含內部企劃、申請手冊、訂房追蹤與 build scripts）
  - `private/private_dashboard.html`
  - `private/confirm.html`（含真實訂單與金流資訊）
  - `private/AFFILIATE_SETUP.md`
  - `private/build_public.sh`
  - `private/index_public.html` / `private/index_sale.html`（build 產物）
- `android/`、`app/`、`store/`、`scripts/`、`capacitor.config.json`、`package.json`、`package-lock.json`

### 部署前自我檢查

每次 push 前執行：

```bash
git ls-files | grep -E "^(private/|confirm\.html|AFFILIATE)" && echo "❌ 私人檔案外洩" || echo "✅ 公開檔案乾淨"
```

若有任何匹配輸出，立即 `git rm --cached <檔案>` 並重新 commit。

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
