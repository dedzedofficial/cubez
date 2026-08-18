# CubeZ — website

The public site for **CubeZ**, the local-first creator toolkit that edits,
captions and publishes short-form video to its operator's own accounts. This is
the site named in the CubeZ TikTok developer application, so the pages here have
to keep saying exactly what the software actually does.

Live at <https://dedzedofficial.github.io/cubez/>.

## Pages

- `index.html` — the CubeZ home page. Browser title is `CubeZ`, and it describes
  the TikTok integration scope by scope.
- `privacy-policy/` — Privacy Policy.
- `terms-of-service/` — Terms of Service.
- `auth/tiktok/` — the TikTok Login Kit callback. TikTok redirects here after the
  operator approves CubeZ; the page shows the one-time authorisation code so the
  operator can paste it into their own copy of CubeZ. It is static, sends the
  code nowhere, and has no server behind it.
- `fishhwb.html`, `dzofo.html` — the FISH HWB pages this repo also hosts, kept
  off the CubeZ pages' navigation so the CubeZ site reads as one product.
- `privacy.html`, `terms.html`, `cubez.html` — redirect stubs for the URLs used
  before the site was restructured.

## TikTok

The developer application must stay in step with these pages:

| TikTok field | Value |
|---|---|
| App name | `CubeZ` |
| Website URL | `https://dedzedofficial.github.io/cubez/` |
| Redirect URI | `https://dedzedofficial.github.io/cubez/auth/tiktok/` |
| Privacy Policy URL | `https://dedzedofficial.github.io/cubez/privacy-policy/` |
| Terms of Service URL | `https://dedzedofficial.github.io/cubez/terms-of-service/` |
| Scopes | `user.info.basic`, `video.publish` |

The `tiktok-developers-site-verification=*.txt` files at the repo root are
TikTok's URL-property verification files. Leave them where they are.

The implementation lives in
[dedzedofficial/CubeZ-Source](https://github.com/dedzedofficial/CubeZ-Source) —
`CubeZ_Poster/poster/publishers/tiktok.py` (upload) and `tiktok_auth.py`
(Login Kit). If the scopes or the flow change there, change them here too.

## Publishing

GitHub Pages serves `main` at the repo root; `.github/workflows/deploy.yml`
handles it. Fonts load from Google Fonts, everything else is local.
