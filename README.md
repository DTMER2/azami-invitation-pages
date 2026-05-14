# azami.coremedica.jp

Static invite landing site for `https://azami.coremedica.jp`.

## Routes

- `/invite/?token=<64-hex-token>` opens the azami app with `azami://azami.coremedica.jp/invite?token=...`.
- The same page calls Supabase RPC `lookup_referral_invite_token` with the public publishable key and displays the 8-character invite code as a fallback.

## Cloudflare Pages

1. Create a Pages project from this repository.
2. Set the build output directory to `/`.
3. Leave the build command empty.
4. Add the custom domain `azami.coremedica.jp`.

## GitHub Pages

Use `.github/workflows/deploy.yml` and set Pages source to GitHub Actions. The workflow publishes the repository root; `CNAME` is already set to `azami.coremedica.jp`.

## DNS

- Cloudflare Pages: add the CNAME value Cloudflare shows for the Pages project.
- GitHub Pages: set `azami.coremedica.jp` as a CNAME to `<owner>.github.io`.

Use only one Pages provider for this hostname at a time.
