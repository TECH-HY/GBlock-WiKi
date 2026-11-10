# TECH-HY platform — security threat model

Source: threat model written for the TECH-HY platform security scan of 2026-11-10 (six repositories, whole-repository scope). Edit this file to steer the next scan; it is the starting point for future threat models.

## Scope and evidence
Repositories scanned: `TECH-HY/techhy-chat` (Laravel 12 / Filament 3 / Inertia-React, gblock.club), `TECH-HY/GBlock` (TanStack Start + Supabase, Lovable-built), `TECH-HY/tradingbot-canonical-v1` (Python, Bybit V5), `TECH-HY/studio-memory` (Python stdlib CLI + markdown cards), `TECH-HY/GBlock-WiKi` (markdown docs), and the infrastructure repository `TECH-HY/vps-infra` (Telegram bot, swarm orchestration, deploy scripts, systemd units for the VPS at 15.235.167.170), added at the owner's request.

No repository has a `SECURITY_MODEL.md`. This model is derived from the code and reuses the component names of the earlier `techhy-chat security threat model` profile (2026-11-01) so findings from both scans line up. Historical evidence, not proof of current state: [PRODUCTION_SECURITY_AUDIT_2026_07_13.md](https://github.com/TECH-HY/techhy-chat/blob/main/docs/gblock/PRODUCTION_SECURITY_AUDIT_2026_07_13.md) (nginx cache leak, unauthenticated `/gblock/register`, public `/gblock/health` audit write) and the vps-infra security review referenced in its README.

## Owner-provided facts (this session, 2026-11-10)
- Scan the **whole** techhy-chat repository; no path exclusions anywhere.
- **Include `TECH-HY/vps-infra`** as the infrastructure repository.
- **GBlock (Lovable/Supabase app) is a prototype or replaced by techhy-chat → lower priority.**
- **Attackers that matter (all selected):** anonymous internet users; registered members/ambassadors abusing referrals or payouts; founders/residents reaching other members' Data Rooms or deals; compromised AI agents / studio sessions with repo or VPS access; malicious insiders/admins. No attacker is ruled out.
- **Accepted risk:** the trading bot runs on Bybit **demo (paper) keys only → its findings are low priority**; **GBlock-WiKi is public documentation → out of scope**. Otherwise "nothing is out of scope; every finding matters".
- Finding tags: **Component**, **CVE**, **CWE**, **Owner** (Studio A / Studio B).
- From the 2026-11-01 techhy-chat model (same owner): KYC/identity/contact data, private deal documents/financial records and deployment credentials/infrastructure control are especially critical; no accepted risk on techhy-chat.

## System overview and trust boundaries
**techhy-chat** is the production platform: one Laravel app with feature-flagged route modules (`routes/web.php`, `routes/gblock.php` ~207 routes, `routes/techhy.php`, `routes/api.php`), MySQL, Redis, local/S3/GCS document storage, queue workers and scheduler, a Filament operator panel, Next/vinext microsites (`sites/`) and a Cloudflare-Workers edge proxy (`edge/`). Deployed to an OVH VPS via `deploy-vps.yml` (appleboy/ssh-action with `VPS_DEPLOY_KEY`) and `deploy/gblock-deploy`.

**vps-infra** is the agent/ops layer on the same VPS family: `bot/tg-zcode-bot.js` runs as **root** under systemd (`User=root`, secrets from `/etc/gblock-vps-bot/secrets.env`), gates commands by Telegram `OWNER_IDS`/`allowed-users.json`, exposes `/deploy` and `/adduser`, spawns zcode/kimi/codex agents, and `bin/gblock-deploy` is the forced command for the CI deploy key (fetch → reset → build → migrate).

**GBlock** is a Supabase-backed TanStack app: RLS policies in `supabase/migrations` (77 policy/has_role statements), server functions in `src/lib/*.functions.ts`, and public hook routes (`src/routes/api/public/hooks/*`, `src/routes/lovable/email/*`) that use `SUPABASE_SERVICE_ROLE_KEY` after comparing the `apikey` header with the **public anon key**; `src/routes/api/public/dev.seed-qa.ts` is a GET seeding endpoint.

**tradingbot-canonical-v1** runs as systemd `canonical-v1-live50` on a separate VPS (51.79.165.158) against Bybit demo; credentials are read from a file outside the repo (`CANON_CREDS`, `/opt/canonical-v1/Partners/API/Bybit_paper_API.txt`); `trendscale150/deploy/install_release.py` runs as sudo and writes systemd units.

**studio-memory** is a CLI (`tools/mem.py`) whose `mem publish` pushes new `inbox/`/`journal/` cards straight to `main`; cards are read by AI agents at thread start (`mem start`), with a secret-regex lint and a documented precedence rule that card text is data, not instructions.

Boundaries: (1) Internet → public pages, auth/intake, webhooks (Telegram, Calendly, CloudMailin, Didit KYC, Stripe, Resend, CSP report) → Laravel/edge; (2) guest → authenticated member → owner/team/capability-scoped resources → operator/admin (Filament, `reauth`, `operator.2fa`); (3) user content/documents/messages → storage, jobs, outbound mail; (4) GitHub PR/CI → exact-SHA deploy → VPS root/deploy key/production secrets; (5) Telegram user → vps-infra bot (root) → agents with repo/VPS access; (6) agent → studio-memory cards → other agents' context; (7) bot process → Bybit API with exchange keys.

## Components (finding tag `Component`)
| Component | Code covered |
|---|---|
| **Public Web** | techhy-chat public routes/controllers, `resources/`, `public/`, `sites/`, `site/`, `sandbox/`, `edge/`; GBlock-WiKi `docs/`, `README.md`, `brand/`. |
| **Identity and KYC** | techhy-chat `app/Services/Auth/`, magic-link/2FA/device middleware (`RequireTrustedAuthHost`, `RequireMemberTwoFactorChallenge`, `RequireRecentAuthentication`, `RefuseErasedAccount`), `modules/KYC/`, `KycWebhookController`, `KybService`, `SanctionsScreeningService`, `config/auth.php`, `config/session.php`. |
| **Marketplace and Data Rooms** | techhy-chat GBlock deal/block/company/Data Room/scoring controllers, services, models, `app/Policies/DataRoom*`, `DataRoomGrantService`, `app/Services/Storage/`, `app/Services/Scoring/`, `config/filesystems.php`. |
| **Payments and Rewards** | techhy-chat wallet/Stripe/subscription/referral/reward/intro-compensation services and controllers, `StripeWebhookController`, `GBlockWalletController`. |
| **Bot and CRM** | techhy-chat `app/Services/Bot/`, `app/Models/Bot/`, Telegram/internal-contact/ecosystem/scheduler API controllers, `config/bot.php`, `config/cloudcode.php`, `vps-bot/`; vps-infra `bot/` (tg-zcode-bot, swarm-router, chat-task-queue) and `bin/swarm-*`, `bin/codex-pool`, `bin/task-watchdog`, `bin/zcode-*`. |
| **Operator Administration** | techhy-chat `app/Filament/`, `RequireFilamentActionPolicy`, `RequireOperatorTwoFactor`, import/export policies, operator routes. |
| **Delivery and Infrastructure** | techhy-chat `.github/workflows/`, `deploy/`, `scripts/`, `docker/`, Dockerfiles/Compose/Caddy/cloudbuild, `bootstrap/`, `app/Jobs/`, `routes/console.php`; vps-infra `bin/gblock-deploy`, `systemd/`, `bot/*.service`; tradingbot `trendscale150/deploy/`. Dependency (CVE) findings belong here unless the vulnerable call sits in a domain component. |
| **GBlock Supabase App** | all of `TECH-HY/GBlock`: `src/`, `supabase/`, `deploy/scripts/`. |
| **Trading Bot** | tradingbot `canonical-v1/sim/` (live50, bybit_client, canon_core, patches), `trendscale150/ts150/`. |
| **Studio Memory** | studio-memory `tools/`, `bin/`, `core/`, `state/`, cards, `eval/`. |

Assign by the vulnerable operation, not the parent directory. Background job findings go to the domain component they touch, else Delivery and Infrastructure.

## Entry points and who can reach them
- Anonymous: techhy-chat marketing, `/projects/*` public catalogue and documents, `/gblock/landing`, access check / registration / scoring apply / venture-club intake, `/api/gblock/v1/session`, `/unsubscribe/{token}`, `/csp-report`, all webhooks (signature-checked: Stripe, Resend/Svix, Didit HMAC, Calendly, CloudMailin basic auth, internal sync tokens with `hash_equals`; fail-closed when the secret is empty). GBlock public hooks (anon-key gate) and `dev/seed-qa`. Telegram users who message the vps-infra bot (`/request` → owner `/adduser`).
- Authenticated members: cabinet, deals/threads, wallet transfers, Data Rooms, scoring reports, KYC flows, capability middleware `gblock.capability:*`, `gblock.market`.
- Operators/admins: Filament panel (`/admin/gblock`), operator refunds (`reauth:600`, `operator.2fa`), imports/exports.
- Machine identities: GitHub Actions deploy key → `gblock-deploy` forced command; Telegram owners → root bot → agent CLIs with repo and VPS access; agents → `mem publish` → main of studio-memory; bot host → Bybit demo API.

## Assets and sensitivity
1. **Critical (owner):** KYC identity evidence and contact/CRM data; private deal documents, Data Room grants, deal threads, scoring submissions; deployment/SSH/database/provider secrets and VPS root; release provenance.
2. **High:** wallet/reward/referral/compensation ledgers, Stripe payment state and webhook authenticity; operator sessions and 2FA; Telegram bot token and `allowed-users.json`; agent API keys in `secrets.env`.
3. **Medium:** GBlock Supabase data (prototype/replaced — lower priority per owner); studio-memory card integrity (prompt-injection surface for agents; secrets leaking into cards).
4. **Low (accepted):** Bybit demo keys and paper P&L; GBlock-WiKi content (public).

## Attacker profiles (all in scope per owner)
Anonymous internet users (enumeration, webhook forgery, cache poisoning, IDOR on public routes); registered members/ambassadors abusing referral attribution, payouts, wallet transfers; founders/residents crossing Data Room / deal boundaries; compromised AI agents or studio sessions holding repo write, deploy-key or VPS access (supply chain via PRs, poisoned memory cards, bot command abuse); malicious or compromised insiders/admins. Exploit preconditions still come from each finding.

## Existing controls observed
Security headers, trusted proxies, CSRF with webhook exceptions, per-route throttles (`ThrottlePerRoute`); magic-link auth with trusted host, 2FA/device challenge, recent-auth and operator 2FA gates; capability middleware and resource policies for Data Rooms; signature-verified webhooks that fail closed on missing secrets; exact-SHA CI-gated deploy via forced-command deploy key; vps-infra bot uses `execFile`/`spawn` argv (one `exec` at line 270), owner/allow-list gating, rate limits, no secrets in repo; GBlock RLS policies and `has_role` RPC; trading bot instance lock, fail-closed reconciliation, demo-host guard; studio-memory secret-regex lint, trust clamping for directly pushed cards, `mem audit`.

## Out of scope / accepted risk
- Trading Bot findings: low priority (demo keys only) unless they expose the host or credentials beyond the demo account.
- GBlock-WiKi: out of scope (public docs); findings there are not worth fixing unless they contain secrets.
- GBlock Supabase App: lower priority (prototype/replaced), not excluded.
- Nothing else is accepted; scanner severities stand elsewhere.

## Reranking rules
Start from the scanner severity. Lower Trading Bot findings one or two levels (to low, or none for pure strategy/accounting logic); dismiss GBlock-WiKi findings (none) unless they leak secrets; lower GBlock Supabase App findings one level. Raise only rarely, for a scanner-confirmed path to a critical asset (KYC data, Data Room documents, deploy/VPS secrets) through an attacker the owner named, and never for findings the scanner calls hard to exploit or unverified. Never reopen dismissed/resolved findings.

## Open questions
- Which VPS hosts the techhy-chat production app today (OVH compose at 15.235.167.170 vs 57.129.153.112), and does the vps-infra bot share a host with production data?
- Is the GBlock Supabase project still deployed with a live `SUPABASE_SERVICE_ROLE_KEY`, or torn down?
- Owner mapping of components to Studio A / Studio B for the `Owner` tag (assumed: techhy-chat/vps-infra/studio-memory → Studio B lanes; trading bot → Studio A).
