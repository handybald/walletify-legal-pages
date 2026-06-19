# Walletify – Marketing & Legal Site

Static GitHub Pages site for [walletify.org](https://www.walletify.org). Turkish-first landing page with an English alternative and all required legal/store URLs.

---

## Pages

| URL | File | Purpose |
|-----|------|---------|
| `/` | `index.md` | Turkish landing page (default) |
| `/en` | `en.html` | English landing page |
| `/privacy` | `privacy.md` | Privacy Policy |
| `/terms` | `terms.md` | Terms of Service |
| `/delete-account` | `delete-account.md` | Account Deletion instructions |
| `/android` | `android.html` | Redirect → Google Play |
| `/ios` | `ios.html` | Redirect → App Store |

---

## Structure

```
walletify-legal-pages/
├── _config.yml           # Jekyll config — do not delete
├── _layouts/
│   └── default.html      # Custom layout (nav, footer, dark theme)
├── assets/
│   └── css/
│       └── style.css     # All styles
├── index.md              # Turkish landing page (/)
├── en.html               # English landing page (/en)
├── android.html          # Store redirect (/android)
├── ios.html              # Store redirect (/ios)
├── privacy.md            # /privacy
├── terms.md              # /terms
├── delete-account.md     # /delete-account
└── CNAME                 # www.walletify.org
```

---

## Publishing with GitHub Pages

1. Create a public repository named `walletify-legal-pages`.
2. Push all files to the `main` branch.
3. Enable GitHub Pages: **Settings → Pages → Deploy from branch → main / (root)**.
4. Wait 1–3 minutes for the build.
5. Verify:
   - `https://www.walletify.org/`
   - `https://www.walletify.org/en`
   - `https://www.walletify.org/privacy`
   - `https://www.walletify.org/terms`
   - `https://www.walletify.org/delete-account`
   - `https://www.walletify.org/android` → Google Play redirect
   - `https://www.walletify.org/ios` → App Store redirect

---

## GitHub Actions secrets (app repository)

Add to the **Walletify app** repo (Settings → Secrets → Actions):

```
PRIVACY_POLICY_URL    = https://www.walletify.org/privacy
TERMS_OF_SERVICE_URL  = https://www.walletify.org/terms
```

---

## Store submission URLs

| Use | URL |
|-----|-----|
| Google Play – Account deletion | `https://www.walletify.org/delete-account` |
| Privacy Policy | `https://www.walletify.org/privacy` |
| Terms of Service | `https://www.walletify.org/terms` |

---

## Updating content

- **Landing page copy** (TR): edit `index.md`
- **Landing page copy** (EN): edit `en.html`
- **Navigation / layout**: edit `_layouts/default.html`
- **Styles**: edit `assets/css/style.css`
- **Legal pages**: edit the relevant `.md` file and push — GitHub Pages rebuilds within minutes

Do not rename or delete `_config.yml` or `CNAME`.

---

## Notes

- No build tools, Node, npm, or React. Static Jekyll only.
- All styles in `assets/css/style.css`; no external CSS frameworks.
- Legal pages are in English. Nav defaults to Turkish (site is Turkish-first).
- Store redirect pages use `<meta http-equiv="refresh">` + `window.location.replace` for broad compatibility.
- Pages are not financial advice. The disclaimer is on all landing pages.
