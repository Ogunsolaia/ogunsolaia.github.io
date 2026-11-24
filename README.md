# Academic website — Isqeel Adesegun Ogunsola

A responsive academic personal website built with **Quarto** and maintained in **RStudio**, for hosting at <https://ogunsolaia.github.io>.

## 1. Open in RStudio

Unzip this project, then open `ogunsolaia-quarto.Rproj` in RStudio. Quarto and Git must be installed on your computer.

## 2. Preview locally

In the **RStudio Terminal** (not the R Console):

```bash
quarto preview
```

Or use the **Render** button in RStudio. For a static build:

```bash
quarto render
```

Generated HTML goes into `_site/`.

## 3. Personalise before publishing

1. Replace `assets/profile-placeholder.svg` with your photo (e.g. `assets/profile.jpg`) and change the image path in `index.qmd`.
2. Add your preferred public email address to `contact.qmd`.
3. Verify the bibliographic metadata and status in `publications.qmd`.
4. Add your real CV as `assets/Isqeel_Ogunsola_CV.pdf` and uncomment the download link in `cv.qmd`.
5. Check all biographical details, dates, teaching descriptions, and news entries.
6. The Modern Violet theme is configured in `styles.css`. Edit its `:root` colour tokens to customise the palette.
7. If your GitHub username or repository name changes, update `site-url` in `_quarto.yml` and the instructions below.

## 4. Publish to GitHub Pages automatically

1. On GitHub, create a **public** repository named exactly `ogunsolaia.github.io` under the account `Ogunsolaia` (GitHub repository names are case-insensitive).
2. In RStudio's Terminal, from this project's folder, run:

```bash
git init
git branch -M main
git add .
git commit -m "Initial Quarto academic website"
git remote add origin https://github.com/Ogunsolaia/ogunsolaia.github.io.git
git push -u origin main
```

If you already created a Git repository or remote, do not repeat `git init` / `git remote add origin`; inspect `git status` and `git remote -v` instead. If the remote has an existing README or commit, reconcile histories before pushing.

3. On GitHub, open **Settings → Pages → Build and deployment → Source**, and choose **GitHub Actions**.
4. The included `.github/workflows/publish.yml` renders the website and deploys `_site/` automatically on pushes to `main`.
5. Watch **Actions** for the build and deployment results. Your site will be available at <https://ogunsolaia.github.io> after a successful deployment and propagation.

For later changes:

```bash
git add .
git commit -m "Update academic website"
git push
```

## Troubleshooting

- `quarto` not found: restart RStudio or ensure Quarto is on PATH.
- `git` not found: install Git and restart RStudio.
- `git push` authentication failure: sign in through Git Credential Manager or configure GitHub authentication; GitHub does not accept account passwords for HTTPS Git operations.
- `quarto render` fails: check YAML indentation and file paths.
- GitHub Pages shows 404: confirm the repository name, Pages source set to GitHub Actions, and the Actions workflow succeeded.
- Missing photo or CV: check exact paths and filename capitalisation (GitHub Actions runs on Linux).

## Design notes

The design is an original Quarto implementation inspired by a clean academic-site aesthetic; it does not copy another website's source code or assets.

## Modern Violet design

This edition uses **primary `#5B3BB5`**, **accent `#A78BFA`**, and **background `#F8F7FF`**. It retains a sidebar profile layout, responsive research cards, accessible focus indicators and reduced-motion support. The homepage profile photo is still a placeholder.

To adjust the design, edit `styles.css`, save and run `quarto preview` again. Do not publish until you have reviewed each page.
