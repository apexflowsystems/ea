# ApexFlow Hosting Package v1

Consistent static deploy of the **full storefront** (same file as `ApexFlow_Full_v1.00.html`).

## What is included

| File | Purpose |
|------|---------|
| `index.html` | **Primary site** — open / host this |
| `ApexFlow_Full_v1.00.html` | Identical copy (backup name) |
| `public-lite.html` | Optional simpler page (if present) |
| `manifest.webmanifest` / `sw.js` | PWA (needs HTTPS) |
| `LICENSE` | Package license |
| `.gitignore` | Git ignore rules |
| `netlify.toml` / `vercel.json` | Static host helpers |
| `.env.example` | Optional backend SMTP hints |

## Features in this build

- Dark storefront + gold market simulation  
- Pricing: **$745 / 12 months**, **$1,499 / 24 months**  
- Checkout: suffix, 3-decimal digits, crypto pay  
- **TXID confirmation** page after payment  
- Receipt email draft → **apexflowsystemsea@gmail.com** (client CC when possible)  
- EA delivery expectation: **0–48 hours** after admin verify  
- Hardcoded wallets (password required to change in Admin)  
- **Staff / Admin** access: top-left **Staff**, Support **Admin sign-in**, footer **Staff**  
- Guest flow has **no public Login**; Admin/KeyGen appear after staff login  

## Payment addresses

| Asset | Address |
|-------|---------|
| Bitcoin | `bc1qdejl4kjf6gnlf7j68edsmvw6re3ca374l2cd7x` |
| USDT (ERC-20) | `0x09b9774FFb7b16abd8Cb7d21B3Cd216C4Fb29b9a` |
| USDC (ERC-20) | `0x09b9774FFb7b16abd8Cb7d21B3Cd216C4Fb29b9a` |

## Staff login

1. Click **Staff** (top-left) or **Support → Admin sign-in**  
2. Email: `admin@apexflow.systems`  
3. Password: set in source as `ADMIN_PASSWORD` (default in this build — **change before public launch**)  
4. Admin panel shows orders, TXIDs, wallets, KeyGen  

Console alternative: `openStaffLogin()`

## Deploy

```bash
# Local preview
python3 -m http.server 8080

# Netlify: drag this folder, or
netlify deploy --dir=. --prod

# Vercel
vercel --prod
```

Upload **all files** in this folder to `public_html` / Pages / Netlify.  
Use **HTTPS** in production.

## Consistency rule

`index.html` and `ApexFlow_Full_v1.00.html` are the **same build**.  
Do not mix older HTML files from previous zips.

## Optional backend

For automatic SMTP (no mail-client popup), deploy `apexflow-backend` separately and set env from `.env.example`.
