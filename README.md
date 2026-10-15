# Omid Edge Panel

**OmidIR · Free For All**

A Cloudflare Workers/Pages panel branded and maintained by **OMIDIRAN**. This edition applies the Omid Edge Panel identity and English interface to the existing EdgeTunnel-based project while retaining the original license, source attribution, protocol markers, and default operational services.

- **Project:** [https://github.com/omidiran-gaming/Omid-Edge-Panel](https://github.com/omidiran-gaming/Omid-Edge-Panel)
- **Telegram:** [https://t.me/omid_gamingORG](https://t.me/omid_gamingORG)
- **YouTube:** [https://www.youtube.com/@omid_Gaming](https://www.youtube.com/@omid_Gaming)
- **Default subscription name:** `OMID-IRAN`
- **Generated config names:** `🟢 OMID-IRAN | ALL 01`, `🔵 OMID-IRAN | MCI-TCI 01` (ECH), and `🟡 OMID-IRAN | MTN-RTL 01` (FinalMask + Cipher Suites). Numbering is independent for each group. FinalMask + Cipher Suites links use `fp=unsafe`.

## Branding in this edition

- Product name: **Omid Edge Panel**
- Short brand: **OmidIR**
- Tagline: **Free For All**
- Footer credit: **Developed by OMIDIRAN**
- UI theme: navy and purple with glass-style surfaces
- Locale: English UI labels in the bundled login and admin pages

## Branded root landing page

The `/` route now serves the OMID-IRAN landing page. It is isolated to ordinary GET/HEAD document requests; the Worker continues to process WebSocket upgrades, `/login`, `/admin`, APIs, subscription routes, and configuration-related paths through the existing routing logic. If an `ASSETS` binding is available the Worker serves the bundled `index.html`, with an embedded copy as a fallback.

## Cloudflare Pages deployment

1. Upload the ZIP contents with `_worker.js` at the root of the deployment. Do not upload a containing folder that nests `_worker.js` one level down.
2. Configure the `ADMIN` environment variable with a strong admin password.
3. Bind a Cloudflare KV namespace with the binding name `KV`.
4. Deploy, then open `/login`; after sign-in, the dashboard is at `/admin`.
5. In **Detailed Configuration → Subscription Name**, save `OMID-IRAN` if an older value is already stored in KV. Existing KV settings are preserved and are not overwritten by a new default.

## Environment variables

| Variable | Purpose |
|---|---|
| `ADMIN` | Administrator password (required for the panel) |
| `KEY` | Optional subscription path key; changing it changes the quick-subscription path |
| `UUID` | Optional fixed UUIDv4 for generated configurations |
| `PROXYIP` | Optional custom proxy IP/host; default behavior remains available if unset |
| `URL` | Optional camouflage-page behavior override |
| `DEBUG` | Set to `1` or `true` to enable debug logging |
| `OFF_LOG` | Set to `1` or `true` to disable KV log recording |
| `BEST_SUB` | Optional preferred-IP subscription generation toggle |
| `PRELOAD_RACE_DIAL` | Optional preloaded race-dial behavior toggle |
| `TCP_CONCURRENT_DIAL` | Optional TCP dial concurrency setting |
| `PROXY_CONCURRENT_DIAL` | Optional proxy dial concurrency setting |

The admin panel also expects the KV binding named `KV`. Do not place real passwords, API keys, or bot tokens in public static assets.

## Compatibility and upstream attribution

This project is a branded derivative of [cmliu/edgetunnel](https://github.com/cmliu/edgetunnel). The original `LICENSE` and historical `CHANGELOG` are retained in this package; the upstream license terms and required notices continue to apply. Branding the interface does not imply authorship of upstream protocol code or third-party tools.

For compatibility, this edition intentionally leaves protocol signature markers, API routes, and upstream preferred-IP, subscription-conversion, and other third-party service endpoints unchanged. The panel's built-in version check, Worker ZIP download, and changelog source are configured to use the project repository: `https://github.com/omidiran-gaming/Omid-Edge-Panel`. The repository must be public and use the `main` branch for these URLs to work. Upload the contents of this package into the repository root (so `_worker.js`, `CHANGELOG`, and `admin/index.html` are at the top level / expected paths) before using the panel's built-in update/apply feature. Until the first complete upload is published, leave that feature unused; the GitHub repository currently needs its files populated.

## Logo

The final custom logo and favicon have not yet been added. They can be placed in a later branding pass without changing the protocol or API logic.
## Cloudflare Pages deployment package

The repository source bundle includes an `OMID-IRAN-Pages/` directory. It contains the Pages deployment files and a ready-to-download `OMID-IRAN-Pages.zip`. Keep this directory and ZIP at those exact paths in the `main` branch; the panel download button points to that ZIP. Deploy the contents of the ZIP with `_worker.js` at the deployment root.
