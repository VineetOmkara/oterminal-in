# Omkara Project Reference
_Last updated: 14 May 2026 — pause checkpoint_

---

## 1. Domains

| Domain | Purpose | Status |
|--------|---------|--------|
| omkarax.com | Omkara Terminal landing page (primary) | Live |
| www.omkarax.com | Same — www redirect | Live |
| oterminal.in | Old domain — still works, same site | Live |
| omkaralens.com | Portfolio Lens dashboard | Live |

DNS provider: GoDaddy  
Hosting: Vercel (GitHub auto-deploy)

---

## 2. GitHub Repos

| Repo | What it is | Deployed URL |
|------|-----------|-------------|
| VineetOmkara/oterminal-in | Omkara Terminal landing page | omkarax.com |
| VineetOmkara/omkara-quant-dashboard | Quant Dashboard | omkara-quant-dashboard.vercel.app/dashboard.html |
| VineetOmkara/Boring-Dashboard | India Inflection Fund | boring-india-inflection-fund.vercel.app |
| VineetOmkara/portfolio-exe | Portfolio Lens | omkaralens.com |

Generate a fresh PAT at github.com/settings/tokens when resuming. Scope needed: repo (full access)

---

## 3. Supabase Projects

| Project | ID | Region | Used by |
|---------|----|--------|---------|
| Portfolio-exe | ucxanvjlfiasaoyvuaeu | ap-south-1 | Portfolio Lens auth + data |
| boring-india-inflection-fund | kfexomhgrswsjahukwvv | ap-south-1 | IIF dashboard |
| vineet@omkaracapital.in Project | fktsoyynillrtxjrfdxx | ap-southeast-1 | General |

Supabase URL (Portfolio Lens): https://ucxanvjlfiasaoyvuaeu.supabase.co

---

## 4. Vercel

- Account: vineet-8290 (Hobby plan)
- Vercel project for terminal: oterminal-in
- All repos connected via GitHub auto-deploy (push to main = live in ~30s)

---

## 5. Omkara Terminal (omkarax.com)

Single-file static site: oterminal-in/index.html

Sections and Cards:
- I — Research: Data Vault, Earnings Hub, Quant
- II — Investments: India Inflection Fund
- III — Operations: Portfolio Lens (live), Finance (soon), Compliance (soon)

Design: cream bg #f1ece1, terra cotta accent #c8643a, fonts: Inter + JetBrains Mono

Back-to-terminal button embedded in:
- Quant Dashboard (public/dashboard.html) — links to omkarax.com
- Boring Dashboard (index.html) — links to omkarax.com

---

## 6. Portfolio Lens (omkaralens.com)

Repo: VineetOmkara/portfolio-exe — file: public/index.html  
Backup branch: backup-14-may-2026

Auth system:
- Supabase Google OAuth
- Email whitelist stored in Supabase table: authorized_emails
- Unauthorized users are auto signed-out
- Admin (vineet@omkaracapital.in) sees Manage Access button in sidebar

Currently authorized emails:
- vineet@omkaracapital.in (admin)
- vb@omkaracapital.in

Tech stack: Single-file HTML, Supabase JS v2, Chart.js, SheetJS, DM Sans font

Google OAuth:
- OAuth redirect URI: https://ucxanvjlfiasaoyvuaeu.supabase.co/auth/v1/callback
- Supabase Site URL: https://www.omkaralens.com

---

## 7. DNS Records

omkarax.com (GoDaddy):
- A @ -> 76.76.21.21
- CNAME www -> cname.vercel-dns.com

oterminal.in (GoDaddy):
- A @ -> 76.76.21.21
- CNAME www -> cname.vercel-dns.com

---

## 8. Pending / Next Steps

- Finance module (Operations) — build when ready
- Compliance module (Operations) — build when ready
- Research Library card — build when ready
- Add more authorized users to Portfolio Lens as team grows

---

## 9. How to Resume with Claude

1. Open a new Cowork session
2. Paste this link: github.com/VineetOmkara/oterminal-in/blob/main/PROJECT_REFERENCE.md
3. Generate a fresh GitHub token at github.com/settings/tokens (scope: repo) and share it
4. Say what you want to work on — Claude will have full context
