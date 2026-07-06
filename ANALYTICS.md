# Website analytics

This site uses **Google Analytics 4 (GA4)** for a free, private analytics
dashboard. Only you (via your Google account) can see the data.

## Your dashboard

- Property tag (Measurement ID): `G-V6477JGNJ6`
- View it at: <https://analytics.google.com/> → select this property
- Useful reports:
  - **Reports → Realtime** — who's on the site right now
  - **Reports → Acquisition → Traffic acquisition** — where visitors come from
    (Google search, LinkedIn, Twitter, direct, referrals, etc.)
  - **Reports → Engagement → Pages and screens** — most-visited pages / "clicks"
  - **Reports → User → Demographics → Country/City** — where visitors are located

Data typically starts appearing within minutes to ~24h after the first visits
following a deploy. To confirm tracking is live, open the site in a browser and
watch **Realtime** — you should see yourself as an active user.

## How it's wired up

- `_quarto.yml` sets `website.google-analytics: "G-V6477JGNJ6"`, so Quarto
  injects the tag into **every** page on each render (`quarto render`).
- The already-built pages in `docs/` were patched directly with the same tag so
  tracking works immediately, before the next rebuild.

> Note: previously the tag lived only in `_includes/analytics.html` and was
> never referenced by `_quarto.yml`, so it fired on the About page only and no
> data was collected elsewhere. That is now fixed.

## Optional: cookie-consent banner (EU/GDPR)

GA4 uses cookies. If you expect EU visitors and want a consent banner, add this
under `website:` in `_quarto.yml` and re-render:

```yaml
  cookie-consent: true
```

## Switching to a privacy-first alternative (also free)

If you'd rather not use Google (no cookies, no consent banner needed):

- **Cloudflare Web Analytics** — <https://www.cloudflare.com/web-analytics/>
  Sign up (free), add your site, copy the beacon **token**.
- **GoatCounter** — <https://www.goatcounter.com/>
  Sign up (free for personal use), copy your site code.

Then replace the GA tag with the provider's script. The simplest route in
Quarto is to put the provider's `<script>` in a file and reference it:

```yaml
format:
  html:
    include-in-header:
      - _includes/analytics.html   # paste the provider snippet here
```

(and remove the `google-analytics:` line). Ask and this can be wired up for you.
