# hb-aeromotive.com

Static site for HB Aeromotive — Harold Bickford's model aircraft business.

## Structure

```
index.html          Main page
assets/css/style.css
assets/js/main.js
```

## Deployment

Hosted on mirrorborn-central (44.248.235.76).
Webroot: `/sites/web/hb-aeromotive.com/`

To deploy:
```bash
rsync -av --exclude='.git' . wbic16@44.248.235.76:/sites/web/hb-aeromotive.com/
```

## Customization

- Update inventory cards in `index.html` → `#inventory` section
- Change contact email from `harold@hb-aeromotive.com` if needed
- Add photos to `assets/img/` and reference them in the cards
