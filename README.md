# kayahirsch.com

Kaya Hirsch's site: a public home page (meet-with-me + products) plus a private, login-gated venture log.

## Pages
- `index.html` — public home page. "Book time with me" request form (no login) and a list of live products, both backed by Supabase. Includes a "Sign in" link in the corner to the venture log.
- `venture-log.html` — private, login-gated build log for tracking startup ideas (Supabase auth).
- `requests.html` — private, login-gated view of incoming meeting requests submitted on the home page.

## Deploy to GitHub Pages
1. Push this repo to GitHub (see chat instructions).
2. In the repo settings, go to Pages, set source to the `main` branch, root folder.
3. Your site will be live at `https://<username>.github.io/<repo-name>/`.

### Custom domain (kayahirsch.com)
A `CNAME` file pointing at `kayahirsch.com` is included. To finish wiring it up:
1. In repo Settings → Pages, confirm the custom domain field shows `kayahirsch.com` (it should pick this up from the `CNAME` file) and enable "Enforce HTTPS" once the certificate is issued.
2. At your domain registrar, point DNS at GitHub Pages — either an `A` record for the apex domain to GitHub's Pages IPs, or a `CNAME` record if you're using a `www` subdomain. See https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site.

## Analytics (PostHog)
`index.html` is wired up to a PostHog project (US Cloud). It tracks page views/autocapture plus custom events: `book_time_clicked`, `meeting_request_submitted`, and `product_link_clicked` (with which product/URL). Check the events in your PostHog dashboard at https://us.posthog.com. The same snippet can be copied into `venture-log.html` to track that tool too — just reuse the same `posthog.init(...)` call.
