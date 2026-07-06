# Deployment — dahoamsmart.de on GitHub Pages

This guide publishes the self-contained `index.html` to **GitHub Pages** and
points the apex domain **dahoamsmart.de** (registered at INWX) at it.

> GitHub account: **varunwell10** · Repository:
> **https://github.com/varunwell10/dahoamsmart**

---

## (a) Create the GitHub repo and push the files

You need `index.html` and `CNAME` (both in this `artifacts/` folder) at the
**root** of the repository.

```bash
# from inside the artifacts/ folder that contains index.html + CNAME
git init
git add index.html CNAME
git commit -m "Launch Dahoam Smart coming-soon page"
git branch -M main

# create the repo on GitHub first (via the web UI or `gh repo create`), then:
git remote add origin https://github.com/varunwell10/dahoamsmart.git
git push -u origin main
```

Notes:
- The `CNAME` file must contain exactly one line: `dahoamsmart.de`. GitHub
  reads it to bind the custom domain. (Setting the domain in the Pages UI also
  creates/updates this file — keep the two in sync.)
- A public repo is fine. Private repos need GitHub Pro/Team for Pages.

## (b) Enable Pages + Enforce HTTPS

1. Repo → **Settings → Pages**.
2. **Build and deployment → Source:** "Deploy from a branch".
3. **Branch:** `main`, folder `/ (root)` → **Save**.
4. Under **Custom domain**, confirm `dahoamsmart.de` is shown (from the CNAME
   file). GitHub runs a DNS check — it goes green once the records below
   propagate.
5. Tick **Enforce HTTPS**. This becomes available after GitHub issues the
   Let's Encrypt certificate for the domain (can take up to ~24 h after DNS is
   correct). Leave it enabled.

## (c) DNS records at INWX (apex domain on GitHub Pages)

In the INWX control panel open **Nameserver / DNS** for `dahoamsmart.de` and
create the following records.

### Apex `dahoamsmart.de` — four A records (IPv4)

| Type | Host / Name | Value            |
|------|-------------|------------------|
| A    | `@`         | `185.199.108.153`|
| A    | `@`         | `185.199.109.153`|
| A    | `@`         | `185.199.110.153`|
| A    | `@`         | `185.199.111.153`|

### Apex `dahoamsmart.de` — four AAAA records (IPv6)

| Type | Host / Name | Value                   |
|------|-------------|-------------------------|
| AAAA | `@`         | `2606:50c0:8000::153`   |
| AAAA | `@`         | `2606:50c0:8001::153`   |
| AAAA | `@`         | `2606:50c0:8002::153`   |
| AAAA | `@`         | `2606:50c0:8003::153`   |

### `www` subdomain — CNAME to your Pages host

| Type  | Host / Name | Value                  |
|-------|-------------|------------------------|
| CNAME | `www`       | `varunwell10.github.io.`|

Notes:
- At INWX, `@` denotes the apex (root) domain; some UIs want the field left
  blank instead — both mean `dahoamsmart.de`.
- Enter the CNAME target as your Pages host `varunwell10.github.io` (the
  trailing dot is optional in most UIs). Do **not** point `www` at an IP.
- Do not add the A/AAAA records to `www`, and do not add a CNAME on the apex
  (`@`) — the apex uses the A/AAAA records above.

## (d) Propagation & certificate

- DNS changes can take anywhere from a few minutes to a few hours to propagate
  (INWX TTL + resolver caches).
- After DNS resolves correctly, GitHub automatically requests a Let's Encrypt
  TLS certificate — issuance can take up to ~24 hours, though it is often much
  faster. Only then can you (and GitHub) enable **Enforce HTTPS**.
- Verify with:
  ```bash
  dig +short dahoamsmart.de A
  dig +short dahoamsmart.de AAAA
  dig +short www.dahoamsmart.de CNAME
  ```
  then load `https://dahoamsmart.de` in a browser.

---

## Security headers — current vs. later

GitHub Pages cannot set custom HTTP response headers, so this page enforces
what it can via `<meta>` tags in `index.html` (Content-Security-Policy and a
referrer policy). Header-only protections such as **HSTS**,
**X-Content-Type-Options: nosniff**, **X-Frame-Options** and
**Permissions-Policy** are not available on Pages.

When you migrate to the planned **EU-hosted VPS (Hetzner/Netcup) with Caddy**,
serve the same file and add the full header set there. Example Caddyfile:

```caddy
dahoamsmart.de, www.dahoamsmart.de {
    root * /var/www/dahoamsmart
    file_server
    encode gzip zstd
    header {
        Strict-Transport-Security "max-age=63072000; includeSubDomains; preload"
        X-Content-Type-Options "nosniff"
        X-Frame-Options "DENY"
        Referrer-Policy "strict-origin-when-cross-origin"
        Permissions-Policy "camera=(), microphone=(), geolocation=()"
        Content-Security-Policy "default-src 'self'; script-src 'self' 'unsafe-inline'; style-src 'self' 'unsafe-inline' https://fonts.googleapis.com; font-src 'self' https://fonts.gstatic.com; img-src 'self' data:; form-action 'self' mailto:; frame-ancestors 'none'; base-uri 'self'; upgrade-insecure-requests"
    }
}
```

Caddy obtains and renews HTTPS certificates automatically. Once migrated,
remember to update the **Hosting** section of the Datenschutzerklärung
accordingly.
