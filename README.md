# SKONGA AI — Legal Center

Static **Terms & Privacy** (English + Kiswahili).

**Repo:** https://github.com/shabanihamidu19-cell/skonga-legal  
**App repo stays separate:** `skonga-prod` / `skonga-ai-v1` (do not mix).

---

## 1. Put the pages in this repo (Termux)

```bash
cd ~
git clone https://github.com/shabanihamidu19-cell/skonga-legal.git
cd skonga-legal

# Use YOUR path to the zip
unzip -o /sdcard/Download/skonga-legal.zip -d /tmp/sklegal

if [ -d /tmp/sklegal/skonga-legal ]; then
  cp -r /tmp/sklegal/skonga-legal/* .
else
  cp -r /tmp/sklegal/* .
fi

ls -la
# expect: index.html terms.html privacy.html terms-sw.html privacy-sw.html assets/

git add -A
git commit -m "Add Terms and Privacy pages"
git push origin main
```

---

## 2. Deploy with GitHub Pages (free HTTPS)

1. Open: https://github.com/shabanihamidu19-cell/skonga-legal/settings/pages  
2. **Source:** Deploy from a branch  
3. **Branch:** `main`  
4. **Folder:** `/ (root)`  
5. **Save**

Wait 1–2 minutes, then open:

| Page | URL |
|------|-----|
| Legal hub | https://shabanihamidu19-cell.github.io/skonga-legal/ |
| Terms (EN) | https://shabanihamidu19-cell.github.io/skonga-legal/terms.html |
| Privacy (EN) | https://shabanihamidu19-cell.github.io/skonga-legal/privacy.html |
| Terms (SW) | https://shabanihamidu19-cell.github.io/skonga-legal/terms-sw.html |
| Privacy (SW) | https://shabanihamidu19-cell.github.io/skonga-legal/privacy-sw.html |

---

## 3. Link from the app

In `skonga-prod` → `www/index.html`, set:

```js
const EXTERNAL_LEGAL = {
  terms: 'https://shabanihamidu19-cell.github.io/skonga-legal/terms.html',
  privacy: 'https://shabanihamidu19-cell.github.io/skonga-legal/privacy.html'
};
```

Play Console / store listing → Privacy policy URL = the privacy.html link above.

---

## 4. Optional: custom domain

Pages → Custom domain → e.g. `legal.skonga.ai` (DNS CNAME to `shabanihamidu19-cell.github.io`).

---

## Files

- `index.html` — hub
- `terms.html` / `privacy.html` — English
- `terms-sw.html` / `privacy-sw.html` — Kiswahili
- `assets/skonga-logo.png`

Before public launch, confirm emails and provider names match your live backend.
