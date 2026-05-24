# Walletify Legal Pages

Static Markdown pages for Walletify's legal URLs, published with GitHub Pages.

---

## Pages

| Page | File | Published URL |
|------|------|---------------|
| Home / index | `index.md` | `https://www.walletify.org/` |
| Privacy Policy | `privacy.md` | `https://www.walletify.org/privacy` |
| Terms of Service | `terms.md` | `https://www.walletify.org/terms` |
| Account Deletion | `delete-account.md` | `https://www.walletify.org/delete-account` |


---

## How to publish with GitHub Pages

1. **Create a public GitHub repository** named exactly `walletify-legal-pages`.

2. **Push all files** in this directory to the `main` branch of that repository. The repository must include `_config.yml` — this file configures Jekyll for clean URLs.

3. **Enable GitHub Pages:**
   - Go to the repository on GitHub.
   - Click **Settings → Pages**.
   - Under **Source**, select **Deploy from a branch**.
   - Set branch to `main`, folder to `/ (root)`.
   - Click **Save**.

4. **Wait 1–3 minutes** for GitHub Pages to build and publish. The published URL will appear at the top of the Settings → Pages screen.

5. **Verify** each URL resolves correctly before using it in store submissions:
   - `https://www.walletify.org/privacy`
   - `https://www.walletify.org/terms`
   - `https://www.walletify.org/delete-account`

---

## GitHub Actions secrets for the Walletify app repository

Once the pages are live, add these two secrets to the **Walletify app** repository  
(Settings → Secrets and variables → Actions → Repository secrets):

```
PRIVACY_POLICY_URL  =  https://www.walletify.org/privacy
TERMS_OF_SERVICE_URL  =  https://www.walletify.org/terms
```

The CI pipeline injects these values into the app binary at build time. No code change is needed — just set the secrets and push to `main`.

---

## Account deletion URL for store submissions

Use this URL in:
- Google Play Console → **App content → Data safety → Account deletion**
- Your Privacy Policy (already linked in the `privacy.md` page)

```
https://www.walletify.org/delete-account
```

---

## Updating the pages

Edit the relevant `.md` file and push to `main`. GitHub Pages will rebuild automatically within a few minutes.

The `_config.yml` file controls the Jekyll theme and URL structure. Do not rename or delete it — removing it breaks the clean URL paths (e.g. `/privacy` instead of `/privacy.html`).

---

## Notes

- These documents cover the current Android / Google Play release. Apple Sign-In and iOS-specific references are included where relevant for a future iOS release.
- These pages are practical release templates. They are not a substitute for legal advice. Review them carefully before submission, especially the SDK list in the Privacy Policy, which must match the SDKs actually shipped in the production binary.
