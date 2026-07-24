# Venture Log

A personal, private build log for tracking startup ideas — Kaya Hirsch.

Live locally via `index.html`. Data is stored in the browser (localStorage), so it stays on whichever device/browser you open it in.

## Deploy to GitHub Pages
1. Push this repo to GitHub (see chat instructions).
2. In the repo settings, go to Pages, set source to the `main` branch, root folder.
3. Your site will be live at `https://<username>.github.io/<repo-name>/`.

### Custom domain (kayahirsch.com)
A `CNAME` file pointing at `kayahirsch.com` is included. To finish wiring it up:
1. In repo Settings → Pages, confirm the custom domain field shows `kayahirsch.com` (it should pick this up from the `CNAME` file) and enable "Enforce HTTPS" once the certificate is issued.
2. At your domain registrar, point DNS at GitHub Pages — either an `A` record for the apex domain to GitHub's Pages IPs, or a `CNAME` record if you're using a `www` subdomain. See https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site.

## Public pages
- `meet.html` — public "meet with me" request form (no login) plus a list of live products, both backed by Supabase.
- `requests.html` — private, login-gated view of incoming meeting requests (same Supabase account as the venture log).

## Analytics (PostHog)
`meet.html` includes a PostHog snippet with a placeholder project key. Sign up at https://posthog.com, grab your Project API Key from Project Settings, and swap it into the `posthog.init(...)` call near the top of `meet.html`. The same snippet can be copied into `index.html` or `maintenance.html` to track those tools too.
