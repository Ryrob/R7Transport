# R-7 Transport — marketing site

Single-file static site for **R7 Enterprises LLC / R-7 Transport** (hotshot vehicle & trailer transport).

- `index.html` — the entire site: markup, CSS, JS, logo (base64), ZIP3 + city geo data, and the instant-quote calculator. No build step, no dependencies, no external requests.
- `.nojekyll` — tells GitHub Pages to serve the file as-is.

## Deploy (GitHub Pages)

Settings → Pages → Source: **Deploy from a branch** → Branch: `main` / root → Save.
Site publishes at `https://ryrob.github.io/R7Transport/`.

## Before launch — replace placeholders

| Placeholder | Where |
|---|---|
| `(555) 555-0177` | phone, all CTAs + `tel:` links |
| `quotes@r7transport.com`, `carriers@r7transport.com` | contact cards, footer |
| `USDOT #0000000`, `MC #000000` | top utility bar, footer badges |
| `1234 Placeholder Way, Suite 100` | footer address |
| Sample lane pricing | `#lanes` section |
| Sample testimonials | `#reviews` section |

## Quote calculator

Rate model lives in the `RATE` object near the top of the inline `<script>`. Tune `minCharge`, the per-mile `tiers`, `vehicleSize`, `enclosed`, `expedite`, `inopFee`, `trailerType` and `spread` to your real cost model. Distances are straight-line between ZIP3/city centroids multiplied by `roadFactor` (1.17).
