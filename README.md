# threads

Static site for the Threads API app — landing page, privacy policy, terms and the
OAuth callback page.

Published at `https://themishkacoder.github.io/threads/`

## Files

| File | Purpose | Used as |
|---|---|---|
| `index.html` | landing page | Website URL, bio link |
| `privacy.html` | privacy policy | Privacy Policy URL |
| `terms.html` | terms of service | Terms of Service URL |
| `callback.html` | shows the OAuth `code`, never redirects | Redirect URI |
| `assets/style.css` | shared styling | — |

## Brand

- Name: **Hardflag**
- Contact: **hardflag@proton.me**

## Replace before publishing

One placeholder remains:

1. `YOURNAME` — beehiiv subdomain, in `index.html` and the footer (`https://YOURNAME.beehiiv.com/subscribe`)

## Meta developer app

Fill these fields with one consistent HTTPS origin:

```
Privacy Policy URL    https://themishkacoder.github.io/threads/privacy.html
Terms of Service URL  https://themishkacoder.github.io/threads/terms.html
Redirect URI          https://themishkacoder.github.io/threads/callback.html
Website URL           https://themishkacoder.github.io/threads/
```

Rules that break the flow if ignored:

- `http://` is rejected, only `https://` works
- `localhost` is rejected for Threads apps
- the redirect URI must match character for character, including any trailing slash
- the page must not redirect — a redirect drops the `code` parameter

## GitHub Pages

Deployment is handled by `.github/workflows/pages.yml` on every push to `main`.
If the first run fails because Pages is not enabled yet, open
`Settings → Pages → Source: GitHub Actions` and re-run the workflow.

## Local preview

```
python3 -m http.server 8000
```

Then open `http://localhost:8000`. Local preview is fine — it is only Meta that
refuses `localhost` as a redirect URI.
