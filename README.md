# Hosting AIVO's Privacy Policy & Terms on GitHub Pages

This folder contains [`privacy.html`](privacy.html) and [`terms.html`](terms.html). Follow these steps once and you'll have stable public URLs to plug into the iOS app and App Store Connect.

## Before you upload — fill in three placeholders

Open both `privacy.html` and `terms.html` and replace these strings everywhere they appear:

| Placeholder | What to put |
|---|---|
| `[CONTACT_EMAIL]` | A real support email you read (e.g. `support@yourdomain.com` or your personal email). |
| `[COMPANY_OR_PERSON_NAME]` | The legal entity providing AIVO — your registered company name, or your personal name if you're a sole developer. |
| `[JURISDICTION]` | Where you live or your company is registered (e.g. "the State of Israel" or "England and Wales"). Used for governing-law clauses. |

Search for `[` in each file to find them all (there are ~5 placeholder occurrences total).

## Create the GitHub repo and host

1. Sign in at <https://github.com> (create an account if you don't have one).
2. Top-right **+** → **New repository**.
   - Repository name: `aivo-legal` (any name works; this name becomes part of the URL).
   - Visibility: **Public** (GitHub Pages requires public for free accounts).
   - Skip "Add a README" — we'll upload our own files.
   - Click **Create repository**.
3. On the empty-repo page, click **uploading an existing file**.
4. Drag `privacy.html` and `terms.html` from this folder onto the upload area.
5. Scroll down → **Commit changes**.
6. In the repo, click **Settings** (top bar) → **Pages** (left sidebar).
7. Under **Build and deployment** → **Source**, pick **Deploy from a branch**.
8. Under **Branch**, select **main** and **/(root)** → **Save**.
9. Wait ~1 minute. Refresh the Pages settings page. A green box will show:
   ```
   Your site is live at https://<your-github-username>.github.io/aivo-legal/
   ```

Your two public URLs are now:

```
https://<your-github-username>.github.io/aivo-legal/privacy.html
https://<your-github-username>.github.io/aivo-legal/terms.html
```

Visit both in a browser to confirm they render.

## Send those two URLs back to the assistant

Paste them in chat. The assistant will swap `LegalLinks.privacyPolicy` and `LegalLinks.terms` in `SettingsView.swift` to point at your real URLs, and you'll use the same URLs in App Store Connect when you fill in the listing (Privacy Policy URL + EULA URL).

## Updating the pages later

Whenever you change the text, edit the file in the GitHub repo (pencil icon on each file), commit. Pages redeploys in a minute. The URLs never change.
