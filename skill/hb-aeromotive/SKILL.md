---
name: hb-aeromotive
description: Update and deploy hb-aeromotive.com — Harold Bickford's model airplane business site. Use when asked to update inventory, contact info, copy, styling, or any content on hb-aeromotive.com. Covers site structure, content editing patterns, and the full deploy workflow to mirrorborn-central (44.248.235.76).
---

# HB Aeromotive Site

Static HTML/CSS site for Harold Bickford's model aircraft business.

- **Repo:** `git@github.com:wbic16/site-hb-aeromotive-com.git`
- **Local clone (ranch/delta-wood):** `/source/site-hb-aeromotive-com/`
- **Webroot on mirrorborn-central:** `/sites/web/hb-aeromotive.com/`
- **Repo mirror on mirrorborn-central:** `/sites/repos/hb-aeromotive.com/`
- **Deploy script:** `/sites/deploy-hb-aeromotive.sh` (on mirrorborn-central)

## Site Structure

```
index.html            Single-page site (all sections)
assets/css/style.css  All styles — CSS variables at :root
assets/js/main.js     Smooth scroll + nav highlight
skill/                This skill (do not deploy to webroot)
```

### Sections in index.html

| Section ID    | Purpose                                 |
|---------------|-----------------------------------------|
| `#inventory`  | Four category cards (ARF/RTF, engines, electronics, parts) |
| `#about`      | Harold's bio blurb + badge              |
| `#contact`    | Email + location                        |

## Common Updates

### Inventory cards
Edit the `.card-grid` div in `index.html`. Each card:
```html
<div class="card">
  <div class="card-icon">✈️</div>
  <h3>Category Name</h3>
  <p>Description of what's available.</p>
</div>
```
Add/remove/rewrite cards freely. Icons are emoji.

### Contact email
Find `harold@hb-aeromotive.com` in `index.html` — appears in both the `href` and visible text.

### Colors / theme
CSS variables in `assets/css/style.css` under `:root`:
- `--navy` / `--blue` / `--sky` — background tones
- `--accent` — gold highlight color (`#e8a020`)

### Adding photos
Put images in `assets/img/`, reference with `<img src="assets/img/filename.jpg">` in the relevant card.

## Deploy Workflow

1. Edit files in `/source/site-hb-aeromotive-com/`
2. Commit and push to `main`:
   ```bash
   cd /source/site-hb-aeromotive-com
   git add -A
   git commit -m "describe change"
   git push
   ```
3. SSH to mirrorborn-central and run the deploy script:
   ```bash
   ssh 44.248.235.76 "/sites/deploy-hb-aeromotive.sh"
   ```
   The script does `git fetch` + `reset --hard origin/main` then rsyncs to webroot.

4. Verify: `curl -sI https://hb-aeromotive.com/ | head -3`

## Notes

- **Git identity for commits:** `Verse <verse@visionquest.me>` (or your own)
- The `skill/` directory lives in the repo but is **not** served — excluded from webroot by rsync is not needed (nginx serves only what's requested, no directory listing).
- Server SSH: `ssh wbic16@44.248.235.76` — key auth, no password.
- Site owner: Harold Bickford (Will's dad). Keep tone friendly, direct, aviation-flavored.

## Reference

See `references/site-map.md` for full section-by-section HTML map.
