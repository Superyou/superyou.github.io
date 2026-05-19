# You Wu Personal Homepage — GitHub Pages Deployment

This package contains both homepage styles:

- `/startup-minimal/` — clean startup/professional style
- `/dark-tech/` — dark AI/chip/security technology style
- `/preview.html` — comparison page for both styles
- `/` root homepage — currently set to `startup-minimal`

## Preview URLs after deployment

After pushing to `https://github.com/Superyou/superyou.github.io`, these should work:

- `https://superyou.github.io/` — current default homepage
- `https://superyou.github.io/preview.html` — style selector / comparison page
- `https://superyou.github.io/startup-minimal/` — startup-minimal sample
- `https://superyou.github.io/dark-tech/` — dark-tech sample

## Deploy from terminal

```bash
cd path/to/superyou.github.io

# optional backup of old site
git checkout -b backup-old-homepage
git add .
git commit -m "Backup old homepage" || true
git checkout main  # or master, depending on your repo

# copy the package files into the repo root, then:
git add .
git commit -m "Update personal homepage after PhD"
git push origin main  # or master
```

## Switch the default style at `/`

GitHub Pages can host both styles at the same time in subfolders, but only one homepage can appear at `https://superyou.github.io/`.

To make **startup-minimal** the default:

```bash
cp startup-minimal/index.html ./index.html
cp startup-minimal/style.css ./style.css
rm -rf assets
cp -R startup-minimal/assets ./assets
git add .
git commit -m "Use startup minimal homepage"
git push
```

To make **dark-tech** the default:

```bash
cp dark-tech/index.html ./index.html
cp dark-tech/style.css ./style.css
rm -rf assets
cp -R dark-tech/assets ./assets
git add .
git commit -m "Use dark tech homepage"
git push
```

## Notes

- No Hugo, Node, Python, or build tool is required.
- These are static HTML/CSS files.
- Keep the folder structure intact so CSS and images load correctly.
