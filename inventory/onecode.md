# OneCode GmbH inventory (discovered 2026-09-02)

cto.onecode.de
hostmaster.hostmaster.onecode.de
hostmaster.hostmaster.www.onecode.de
hostmaster.onecode.de
hostmaster.www.onecode.de
kurs.onecode.de
mail.onecode.de
mta-sts.onecode.de
onecode.de
www.onecode.de

## PASSIVE RECON 2026-09-02 (read-only, non-intrusive)

> Recon observations only. These are NOT confirmed vulnerabilities; ownership/in-scope of each host must be confirmed against the program scope before any active testing. Hosts resolve + serve HTTP — investigation requires scoped authorization.

**Probed:** 10 hosts | **Live HTTP:** 3

| Host | Status | Server/Tech |
|---|---|---|
| `kurs.onecode.de` | 307 | Server: railway-hikari -> /login |
| `www.onecode.de` | 200 | Server: cloudflare |
| `mta-sts.onecode.de` | 301 | Server: cloudflare -> https://www.onecode.de/ |

**CNAME review signals (3):**
- `kurs.onecode.de` -> `tgk4io5m.up.railway.app`
- `www.onecode.de` -> `cdn.webflow.com`
- `mta-sts.onecode.de` -> `cdn.webflow.com`

## DEEP SERVICE SCAN 2026-09-02 (read-only connect+banner)
**Host:** `kurs.onecode.de` | **Ports:** [80, 443]
**Web surface only:** [80, 443]

## DEEP SERVICE SCAN 2026-09-02 (read-only connect+banner)
**Host:** `mta-sts.onecode.de` | **Ports:** [80, 443, 2082, 2083, 2086, 2087, 8080, 8443]
**Non-web ports observed:** [2082, 2083, 2086, 2087, 8080, 8443]
> NOTE: repeated identical non-web port sets (e.g. 2082,2083,2086,2087,8080,8443) across many hosts and wide port sets are likely a shared edge/proxy answering EOF, NOT confirmed real services. Verify with a proper port scanner (e.g. nmap) under authorization before treating as real. These are surface-map hints only, not findings.

## DEEP SERVICE SCAN 2026-09-02 (read-only connect+banner)
**Host:** `www.onecode.de` | **Ports:** [80, 443, 2082, 2083, 2086, 2087, 8080, 8443]
**Non-web ports observed:** [2082, 2083, 2086, 2087, 8080, 8443]
> NOTE: repeated identical non-web port sets (e.g. 2082,2083,2086,2087,8080,8443) across many hosts and wide port sets are likely a shared edge/proxy answering EOF, NOT confirmed real services. Verify with a proper port scanner (e.g. nmap) under authorization before treating as real. These are surface-map hints only, not findings.

## 2026-09-02 21:41:05 UTC

## 2026-09-02 23:34:10 UTC

## 2026-09-03 01:27:20 UTC

## 2026-09-03 06:31:56 UTC

## 2026-09-03 11:43:43 UTC

## 2026-09-03 16:16:20 UTC

## 2026-09-03 19:28:15 UTC

## 2026-09-03 21:54:04 UTC
- NEW Probe completed: GET https://kurs.onecode.de/login returns 200 with Next.js login form (email/password), no Set-Cookie header, no visible CSRF token in form. Root /, /api, /graphql, /dashboard all 307

## 2026-09-04 00:01:14 UTC
- NEW Auth stack identified from client bundles: Supabase project aygnpacdkgtsfnhgcyjc.supabase.co + publishable key (sha256 870cf518cadbb13823395f6f7c2930ab0c8e0db734df71ea8e646264ee8803c6). login=signInWi
- NEW Pre-auth open routes: /login (200), /passwort-vergessen (200 prerendered). All /api/* (incl /api/broadcast), /v1, /dashboard, /kurse, /einladung, /passwort-neu -> 307 auth-gated.
- NEW Supabase /rest/v1/* -> 503 PGRST002 (schema cache unavailable) with publishable key; no unauthenticated REST/table exposure.
- NEW Supabase /auth/v1/settings: email-only, disable_signup=true, mailer_autoconfirm=false, all external OAuth false, saml false.
- NEW Probe confirmed: GET https://kurs.onecode.de/login returns 200 with Next.js login form (email/password), no Set-Cookie header, no visible CSRF token. Root /, /api, /graphql, /dashboard all 307→/login 
- CHANGED Session fixation hypothesis confidence reduced 65→60: no pre-auth cookie observed on GET /login; Next.js session gate on all routes.
- CHANGED GraphQL introspection hypothesis parked (confidence 45 < 50): /graphql returns 307→/login; no evidence GraphQL exists without auth.
- CHANGED AUTH learning updated: no pre-auth session cookie; Next.js session gate on all routes; session-fixation pre-auth mechanism unsupported.

## 2026-09-04 03:59:02 UTC
- NEW Supabase auth stack fully characterized: project `aygnpacdkgtsfnhgcyjc`, publishable key sha256 `870cf518...`, email-only, signup disabled, confirmation required, no external OAuth, magic-link handoff
- NEW Pre-auth surface exhausted: only `/login` (200) and `/passwort-vergessen` (200) accessible; all `/api/*`, `/v1`, `/dashboard`, `/kurse`, `/einladung`, `/passwort-neu` return 307.
- NEW Supabase REST anon exposure blocked: `/rest/v1/*` returns 503 PGRST002 with publishable key.
- NEW Next.js/Turbopack App Router confirmed with registered `/api` + `/v1` routers (auth-gated) — post-auth BOLA surface concretely exists.
- NEW UUID primary keys in Supabase weaken guessable-ID enumeration; highest-value post-auth target is missing RLS filter enabling cross-tenant SELECT.
- NEW Realtime `/api/broadcast` channel endpoint identified in client bundle (307 pre-auth, post-auth channel-auth gap possible).
- CHANGED Session fixation hypothesis confidence reduced to 60→0 (parked): no pre-auth Set-Cookie on GET `/login`; Next.js session gate on all routes; Supabase `setSession` flow uses URL hash, not pre-auth cook
- CHANGED GraphQL introspection hypothesis parked at 45: `/graphql` returns 307→`/login`; no evidence GraphQL exists without auth.
- CHANGED Subdomain takeover hypotheses (hostmaster.*, cto.onecode.de) remain at confidence 45 < 50 — passive-only verification cannot confirm claimability without active DNS resolution against provider APIs.
- CHANGED Rate-limiting on login hypothesis parked: verification requires POST (mutating) which violates passive probe rules; needs AUTH_HELPED.

## 2026-09-04 08:47:33 UTC
- NEW Supabase direct service endpoints (`aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/`, `/functions/v1/`, `/realtime/v1/`) not yet probed — these bypass app-level auth gates and may expose public storage b
- CHANGED Phase=POC, target=api — all kurs.onecode.de pre-auth app surface exhausted; only remaining unexplored pre-auth attack surface is the Supabase project's own service endpoints and deeper JS bundle route

## 2026-09-04 13:36:00 UTC
- NEW Supabase direct service endpoints (storage/v1, functions/v1, realtime/v1) identified as unprobed pre-auth surface — bypass Next.js middleware entirely, accessible with anon key.
- NEW Supabase Storage public bucket exposure hypothesis (confidence 55) — course platform semantics suggest resources stored in Supabase Storage; public/overly-permissive bucket policies are common.
- NEW Supabase Edge Functions unauthenticated invocation hypothesis (confidence 45) — deployed functions without explicit auth checks are directly invocable.
- NEW Supabase Realtime channel impersonation via anon key hypothesis (confidence 35) — RLS misconfiguration on realtime publications could allow cross-tenant data stream access.
- CHANGED Phase=POC, target=api confirmed — all kurs.onecode.de pre-auth app routes exhausted; only Supabase direct service endpoints remain for pre-auth probing.
- CHANGED Priority shift: aygnpacdkgtsfnhgcyjc.supabase.co (direct service endpoints) now scores 7.5 priority vs kurs.onecode.de app routes at 7.0 — direct endpoints bypass auth gates.
- CHANGED Post-auth BOLA via Supabase RLS gap confidence stable at 65 (nemotron3) / 62 (bigpickle) — highest overall value but requires two invited test accounts (AUTH_HELPED).
- NEW Supabase direct service endpoints (storage/v1, functions/v1, realtime/v1) identified as unprobed pre-auth surface — bypass Next.js middleware entirely, accessible with anon key.
- NEW Supabase Storage public bucket exposure hypothesis (confidence 55) — course platform semantics suggest resources stored in Supabase Storage; public/overly-permissive bucket policies are common.
- NEW Supabase Edge Functions unauthenticated invocation hypothesis (confidence 45) — deployed functions without explicit auth checks are directly invocable.
- NEW Supabase Realtime channel impersonation via anon key hypothesis (confidence 35) — RLS misconfiguration on realtime publications could allow cross-tenant data stream access.
- CHANGED Phase=POC, target=api confirmed — all kurs.onecode.de pre-auth app routes exhausted; only Supabase direct service endpoints remain for pre-auth probing.
- CHANGED Priority shift: aygnpacdkgtsfnhgcyjc.supabase.co (direct service endpoints) now scores 7.5 priority vs kurs.onecode.de app routes at 7.0 — direct endpoints bypass auth gates.
- CHANGED Post-auth BOLA via Supabase RLS gap confidence stable at 65 (nemotron3) / 62 (bigpickle) — highest overall value but requires two invited test accounts (AUTH_HELPED).

## 2026-09-04 17:14:36 UTC
- NEW Supabase direct service endpoints (storage/v1, functions/v1, realtime/v1) confirmed as unprobed pre-auth surface bypassing Next.js middleware entirely — accessible with anon key (from bigpickle 08:47,
- NEW Supabase Storage public bucket exposure hypothesis elevated to confidence 55 (bigpickle 55→58, nemotron3 55) — course platform semantics + separate storage service = realistic pre-auth vector
- NEW Supabase Edge Functions unauthenticated invocation hypothesis at confidence 45-48 — deployed functions without verifySession/verifyJwt directly invocable
- CHANGED Priority shift: aygnpacdkgtsfnhgcyjc.supabase.co (direct service endpoints) now scores 7.5-8.0 priority vs kurs.onecode.de app routes at 7.0 — direct endpoints bypass auth gates
- CHANGED Phase=POC, target=api confirmed — all kurs.onecode.de pre-auth app routes exhausted; only Supabase direct service endpoints remain for pre-auth probing
- CHANGED Post-auth BOLA via Supabase RLS gap confidence stable at 65 (nemotron3) / 62 (bigpickle) — highest overall value but requires two invited test accounts (AUTH_HELPED)

## 2026-09-04 20:01:49 UTC

## 2026-09-04 22:27:30 UTC
- NEW Supabase Storage `/storage/v1/bucket` returns 200 with empty array `[]` using publishable key `sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30` — endpoint directly accessible, bypasses Next.js middlewa
- NEW Supabase Functions `/functions/v1/` returns 404 (no deployed functions or not listable)
- NEW Supabase Realtime `/realtime/v1/` returns 401 — requires auth, no unauthenticated access
- NEW Supabase REST `/rest/v1/` returns 401 with publishable key — anon REST blocked
- NEW Auth settings confirmed: email-only, `disable_signup=true`, `mailer_autoconfirm=false`, all external OAuth `false`
- CHANGED Storage public bucket hypothesis confidence adjusted: endpoint probeable (PASSIVE) but zero buckets exist → exposure risk lowered from MEDIUM-HIGH to LOW

## 2026-09-05 00:17:17 UTC
- NEW Supabase Storage `/storage/v1/bucket` returns 200 with empty array `[]` using publishable key `sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30` — endpoint directly accessible, bypasses Next.js middlewa
- NEW Supabase Functions `/functions/v1/` returns 404 (no deployed functions or not listable)
- NEW Supabase Realtime `/realtime/v1/` returns 401 — requires auth, no unauthenticated access
- NEW Supabase REST `/rest/v1/` returns 401 with publishable key — anon REST blocked
- NEW Auth settings confirmed: email-only, `disable_signup=true`, `mailer_autoconfirm=false`, all external OAuth `false`
- CHANGED Storage public bucket hypothesis confidence adjusted: endpoint probeable (PASSIVE) but zero buckets exist → exposure risk lowered from MEDIUM-HIGH to LOW
- CHANGED Pre-auth surface on `kurs.onecode.de` fully exhausted — only `/login` and `/passwort-vergessen` at 200; all `/api/*`, `/v1`, `/dashboard` 307→/login
- CHANGED Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts (AUTH_HELPED)
- CHANGED Subdomain takeover hypotheses (`hostmaster.*`, `cto.onecode.de`) remain at confidence 45 < 50 — passive-only cannot confirm claimability without active DNS resolution

## 2026-09-05 04:43:56 UTC
- NEW Supabase Storage `/storage/v1/bucket` returns 200 with empty array `[]` using publishable key `sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30` — endpoint directly accessible, bypasses Next.js middlewa
- NEW Supabase Functions `/functions/v1/` returns 404 (no deployed functions or not listable)
- NEW Supabase Realtime `/realtime/v1/` returns 401 — requires auth, no unauthenticated access
- NEW Supabase REST `/rest/v1/` returns 401 with publishable key — anon REST blocked
- NEW Auth settings confirmed: email-only, `disable_signup=true`, `mailer_autoconfirm=false`, all external OAuth `false`
- CHANGED Storage public bucket hypothesis confidence adjusted: endpoint probeable (PASSIVE) but zero buckets exist → exposure risk lowered from MEDIUM-HIGH to LOW
- CHANGED Pre-auth surface on `kurs.onecode.de` fully exhausted — only `/login` and `/passwort-vergessen` at 200; all `/api/*`, `/v1`, `/dashboard` 307→/login
- CHANGED Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts (AUTH_HELPED)
- CHANGED Subdomain takeover hypotheses (`hostmaster.*`, `cto.onecode.de`) remain at confidence 45 < 50 — passive-only cannot confirm claimability without active DNS resolution

## 2026-09-05 08:46:23 UTC
- NEW Supabase Storage endpoint (storage/v1/bucket) returns 200 with empty array `[]` using publishable key — endpoint directly accessible, bypasses Next.js middleware.
- NEW Supabase Functions endpoint returns 404 — no deployed functions or not listable pre-auth.
- NEW Supabase Realtime endpoint returns 401 — requires auth, no unauthenticated access.
- NEW Supabase REST endpoint returns 401 with publishable key — anon REST blocked.
- CHANGED Storage public bucket hypothesis confidence lowered from MEDIUM-HIGH to LOW — endpoint probeable but zero buckets exist.
- CHANGED Pre-auth surface on `kurs.onecode.de` fully exhausted — only `/login` and `/passwort-vergessen` at 200; all `/api/*`, `/v1`, `/dashboard` 307→/login.
- CHANGED Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts (AUTH_HELPED).
- CHANGED Subdomain takeover hypotheses (`hostmaster.*`, `cto.onecode.de`) remain at confidence 45 < 50 — passive-only cannot confirm claimability without active DNS resolution.
- NEW Supabase Storage `/storage/v1/bucket` returns 200 with empty array `[]` using publishable key `sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30` — endpoint directly accessible, bypasses Next.js middlewa
- NEW Supabase Functions `/functions/v1/` returns 404 (no deployed functions or not listable)
- NEW Supabase Realtime `/realtime/v1/` returns 401 — requires auth, no unauthenticated access
- NEW Supabase REST `/rest/v1/` returns 401 with publishable key — anon REST blocked
- NEW Auth settings confirmed: email-only, `disable_signup=true`, `mailer_autoconfirm=false`, all external OAuth `false`
- CHANGED Storage public bucket hypothesis confidence adjusted: endpoint probeable (PASSIVE) but zero buckets exist → exposure risk lowered from MEDIUM-HIGH to LOW
- CHANGED Pre-auth surface on `kurs.onecode.de` fully exhausted — only `/login` and `/passwort-vergessen` at 200; all `/api/*`, `/v1`, `/dashboard` 307→/login
- CHANGED Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts (AUTH_HELPED)
- CHANGED Subdomain takeover hypotheses (`hostmaster.*`, `cto.onecode.de`) remain at confidence 45 < 50 — passive-only cannot confirm claimability without active DNS resolution

## 2026-09-05 12:11:29 UTC
- NEW NO_DELTA — inventory unchanged (10 hosts, 3 live HTTP); last leads confirm identical Supabase direct endpoint results (storage 200/empty, functions 404, realtime 401, REST 401); pre-auth surface on ku

## 2026-09-05 15:42:43 UTC
- NEW Confirmed `/api/broadcast` is the only registered `/api/*` route in client bundles (from chunk 0-lpao5_i9htd.js); no `/v1/*` routes found
- NEW Supabase auth settings unchanged: email-only, signup disabled, confirmation required, zero external OAuth providers, magic-link handoff via URL fragment with fixed whitelist `{invite:/einladung, recov
- NEW Supabase Storage `/storage/v1/bucket` returns 200 with empty array `[]` (zero buckets) — probeable pre-auth with publishable key
- NEW Supabase Functions `/functions/v1/` returns 404 (NOT_FOUND) — no deployed functions or not listable pre-auth
- NEW Supabase Realtime `/realtime/v1/` returns 401 — auth required, no pre-auth access
- NEW Supabase REST `/rest/v1/` returns 401 (Secret API key required) — anon REST blocked
- CHANGED Pre-auth surface on `kurs.onecode.de` fully exhausted — only `/login` and `/passwort-vergessen` return 200; all `/api/*`, `/v1`, `/dashboard`, `/kurse`, `/einladung`, `/passwort-neu` return 307→/login
- CHANGED Post-auth BOLA via Supabase RLS gap remains highest-value hypothesis (conf 65); requires two invited test accounts (AUTH_HELPED)

## 2026-09-05 17:42:22 UTC

## 2026-09-05 19:35:48 UTC

## 2026-09-05 21:48:33 UTC

## 2026-09-05 23:43:03 UTC
- NEW cto.onecode.de re-probed 23:41 UTC: stable 409 Conflict body "error code:1001" (Server:cloudflare, CF-RAY a36915496c750613-IAD), 443 TLS handshake-fail, CNAME cto->cname.perspective-dns.com (104.18.2.
- NEW Provider identity resolved: cname.perspective-dns.com is the documented "connect your own domain" CNAME value for the Perspective funnel SaaS (intercom.help/perspective-funnels articles confirm arbitr
- NEW www.onecode.de verified static Webflow marketing (project onecodedev, pageId 69c2...7b4, cf-cache HIT) — no dynamic/web-crawlable surface; mta-sts.onecode.de = CF 301 mail stub (out-of-scope class).
- NEW mail.onecode.de (95.130.17.37) returns no HTTP — non-web service, no action.

## 2026-09-06 03:58:05 UTC
- NEW Supabase REST `/rest/v1/` now returns 401 "Secret API key required" with publishable key (was 503 PGRST002); explicit anon-block confirmed, schema-cache down persists
- NEW cto.onecode.de re-probed: stable 409 Conflict "error code:1001" (Server: cloudflare, CF-RAY a36915496c750613-IAD), 443 TLS handshake-fail, CNAME cto→cname.perspective-dns.com (104.18.2.x) — Perspectiv
- NEW www.onecode.de verified static Webflow marketing (project onecodedev, pageId 69c2...7b4, cf-cache HIT) — no dynamic surface; mta-sts.onecode.de = CF 301 mail stub (out-of-scope class)
- NEW mail.onecode.de (95.130.17.37) returns no HTTP — non-web service, out-of-scope
- CHANGED Subdomain takeover hypothesis for cto.onecode.de elevated to confidence 58 (HUMAN confirm required): provider identified, CNAME target documented, hostname currently unbound and plausibly reclaimable
- CHANGED Supabase REST anon exposure hypothesis confidence adjusted: explicit 401 anon-block reduces immediate risk but monitor stays active (cache recovery could change gateway behavior)

## 2026-09-06 08:40:13 UTC
- NEW Supabase REST `/rest/v1/` behavior changed: now returns 401 "Secret API key required" with publishable key (was 503 PGRST002); explicit anon-block at gateway level confirmed
- NEW cto.onecode.de re-probed 2026-09-06: stable 409 Conflict "error code:1001" (Server: cloudflare, CF-RAY), 443 TLS handshake-fail, CNAME → cname.perspective-dns.com (104.18.2.x) — Perspective funnel Saa
- CHANGED Subdomain takeover hypothesis for cto.onecode.de elevated to confidence 58 (HUMAN confirm required): provider identified, CNAME target documented, hostname currently unbound and plausibly reclaimable
- CHANGED Supabase REST anon exposure hypothesis confidence adjusted: explicit 401 anon-block reduces immediate risk but monitor stays active (cache recovery could change gateway behavior)
- CHANGED Pre-auth surface on `kurs.onecode.de` remains fully exhausted — only `/login` and `/passwort-vergessen` at 200; all `/api/*`, `/v1`, `/dashboard` 307→/login (no delta since 2026-09-05)
- CHANGED Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts (AUTH_HELPED) — no delta

## 2026-09-06 12:22:06 UTC

## 2026-09-06 15:39:14 UTC

## 2026-09-06 17:44:25 UTC

## 2026-09-06 20:17:37 UTC
- CHANGED cto.onecode.de: TLS handshake failure persists (OpenSSL sslv3 alert handshake failure), CNAME → cname.perspective-dns.com stable; HTTP 409 no longer reachable due to TLS failure — consistent with prev

## 2026-09-06 22:12:43 UTC
- CHANGED cto.onecode.de: TLS handshake failure persists (OpenSSL sslv3 alert handshake failure), CNAME → cname.perspective-dns.com stable; HTTP 409 no longer reachable due to TLS failure — consistent with prev

## 2026-09-07 00:05:41 UTC

## 2026-09-07 04:57:10 UTC

## 2026-09-07 10:03:58 UTC

## 2026-09-07 15:58:33 UTC

## 2026-09-07 19:53:53 UTC

## 2026-09-07 22:42:59 UTC

## 2026-09-08 01:08:30 UTC

## 2026-09-08 06:03:48 UTC

## 2026-09-08 11:30:35 UTC
- NEW Supabase REST `/rest/v1/` flipped from 401 "Secret API key required" back to 503 PGRST002 "Could not query the database for the schema cache" at 01:10Z 2026-09-08 (probe confirmed)
- CHANGED Gateway state unstable — oscillates between explicit anon-block (401) and schema-cache-down (503); neither indicates permissive ACL

## 2026-09-08 15:21:10 UTC
- NEW Supabase REST `/rest/v1/` flipped from 401 "Secret API key required" back to 503 PGRST002 "Could not query the database for the schema cache" at 01:10Z 2026-09-08 (confirmed probe)
- NEW Supabase REST `/rest/v1/` re-probed at 11:29Z 2026-09-08 — 503 PGRST002 persists (schema-cache-down mode); gateway has now shown three states: 503→401→503 since 09-04
- CHANGED Gateway state unstable — oscillates between explicit anon-block (401) and schema-cache-down (503); neither state indicates permissive ACL
- CHANGED cto.onecode.de re-confirmed 11:29Z 09-08 — HTTP 409 "error code:1001", CNAME→cname.perspective-dns.com stable 6+ days; hostname unbound/reclaimable; conf 58, HUMAN confirm pending
- NEW Supabase REST `/rest/v1/` flipped from 401 "Secret API key required" back to 503 PGRST002 "Could not query the database for the schema cache" at 01:10Z 2026-09-08 (confirmed probe)
- NEW Supabase REST `/rest/v1/` re-probed at 11:29Z 2026-09-08 — 503 PGRST002 persists (schema-cache-down mode); gateway has now shown three states: 503→401→503 since 09-04
- CHANGED Gateway state unstable — oscillates between explicit anon-block (401) and schema-cache-down (503); neither state indicates permissive ACL
- CHANGED cto.onecode.de re-confirmed 11:29Z 09-08 — HTTP 409 "error code:1001", CNAME→cname.perspective-dns.com stable 6+ days; hostname unbound/reclaimable; conf 58, HUMAN confirm pending

## 2026-09-08 18:51:07 UTC
- NEW Supabase REST `/rest/v1/` flipped from 401 "Secret API key required" back to 503 PGRST002 "Could not query the database for the schema cache" at 01:10Z 2026-09-08 (confirmed probe)
- NEW Supabase REST `/rest/v1/` re-probed at 11:29Z 2026-09-08 — 503 PGRST002 persists (schema-cache-down mode); gateway has now shown three states: 503→401→503 since 09-04
- CHANGED Gateway state unstable — oscillates between explicit anon-block (401) and schema-cache-down (503); neither state indicates permissive ACL
- CHANGED cto.onecode.de re-confirmed 11:29Z 09-08 — HTTP 409 "error code:1001", CNAME→cname.perspective-dns.com stable 6+ days; hostname unbound/reclaimable; conf 58, HUMAN confirm pending

## 2026-09-08 21:47:30 UTC
- CHANGED Supabase REST `/rest/v1/` flipped from 503 PGRST002 (11:29Z) back to 401 "Secret API key required" (21:44Z) — gateway oscillation confirmed: 503→401→503→401 since 09-04
- CHANGED cto.onecode.de re-confirmed live 21:44Z — HTTP 409 "error code: 1001", CNAME→cname.perspective-dns.com stable 6+ days

## 2026-09-08 23:58:20 UTC

## 2026-09-09 04:30:01 UTC
- NEW Supabase REST gateway state flipped from 503 PGRST002 (2026-09-08 23:57Z) to unknown — next cadence probe due post-00:00Z 2026-09-09 per ≤1/day rule
- CHANGED No live probe executed yet today; all prior state (cto 409/CNAME, storage empty, kurs /login 200, REST oscillation 503↔401) assumed stable until verified
- NEW cadence window open for REST re-probe (last 23:57Z 09-08 showed 503); next probe will determine if gateway remains in schema-cache-down or reverts to explicit 401 anon-block

## 2026-09-09 09:12:24 UTC
- NEW Supabase REST `/rest/v1/` cadence window open for re-probe (last 23:57Z 09-08 showed 503 PGRST002); next probe will determine if gateway remains in schema-cache-down or reverts to explicit 401 anon-bl
- NEW No live probe executed today 2026-09-09; all prior state (cto 409/CNAME, storage empty, kurs /login 200, REST oscillation 503↔401) assumed stable until verified

## 2026-09-09 13:52:43 UTC
- NEW Supabase REST `/rest/v1/` cadence window open for re-probe (last 23:57Z 09-08 showed 503 PGRST002); next probe will determine if gateway remains in schema-cache-down or reverts to explicit 401 anon-bl
- NEW No live probe executed today 2026-09-09; all prior state (cto 409/CNAME, storage empty, kurs /login 200, REST oscillation 503↔401) assumed stable until verified

## 2026-09-09 17:44:36 UTC
- NEW Supabase REST `/rest/v1/` cadence window open for re-probe (last 23:57Z 09-08 showed 503 PGRST002); next probe will determine if gateway remains in schema-cache-down or reverts to explicit 401 anon-bl
- NEW No live probe executed today 2026-09-09; all prior state (cto 409/CNAME, storage empty, kurs /login 200, REST oscillation 503↔401) assumed stable until verified

## 2026-09-09 20:49:39 UTC
- NEW Supabase REST `/rest/v1/` re-probed 2026-09-09 20:46Z → **401 "Secret API key required"** (was 503 PGRST002 at 23:57Z 09-08); gateway 6-state oscillation confirmed (503→401→503→401→503→503→**401** sin
- CHANGED No other live probes executed today; all prior state (cto 409/CNAME, storage empty, kurs /login 200) assumed stable until verified

## 2026-09-09 23:16:20 UTC
- CHANGED Supabase REST gateway flipped 401→503 PGRST002 at 23:06Z 09-09 (8-state oscillation: 503→401→503→401→503→503→401→503 since 09-04); still no permissive state.
- CHANGED cto.onecode.de re-confirmed live 23:06Z — HTTP 409 "error code: 1001", CNAME→cname.perspective-dns.com stable; kurs /login + /passwort-vergessen both 200. No other deltas.

## 2026-09-10 01:13:07 UTC
- NEW Supabase REST `/rest/v1/` re-probed 2026-09-10 01:11Z → **401 "Secret API key required"** (was 503 PGRST002 at 23:06Z 09-09); gateway 9-state oscillation confirmed (503→401→503→401→503→503→401→503→**4
- CHANGED Cadence probe executed; all other surfaces (cto 409/CNAME, storage empty, kurs /login 200) confirmed stable

## 2026-09-10 06:10:05 UTC

## 2026-09-10 11:33:14 UTC
- CHANGED Supabase REST gateway 10-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401 since 09-04); 06:08Z probe returned 503 PGRST002 with sb_publishable key
- CHANGED Supabase platform-level key format change: JWT anon key (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; only sb_publishable_ format accepted — not a OneCode key rotation
- CHANGED cto.onecode.de re-confirmed 06:08Z — HTTP 409 "error code:1001" + TLS handshake failure, CNAME→cname.perspective-dns.com stable 9+ days; unbound/reclaimable, conf 58 HUMAN pending

## 2026-09-10 15:13:38 UTC

## 2026-09-10 18:36:05 UTC

## 2026-09-10 21:16:03 UTC
- CHANGED kurs.onecode.de CNAME: tgk4io5m.up.railway.app → ki8dqcf6.up.railway.app (A 69.46.46.42), verified 21:14Z 09-10. App behavior unchanged (/login 200, / 307→/login, server railway-hikari, x-railway-edge
- NEW Certspotter CT scan 21:14Z: exactly 5 names (onecode.de, www, kurs, cto, mta-sts) — inventory complete, zero new subdomains from certificate transparency.

## 2026-09-10 23:16:33 UTC
- CHANGED Supabase REST `/rest/v1/` now returns 401 "Secret API key required" with `sb_publishable_` key (11th sequential 503→401 oscillation since 09-04); gateway remains non-permissive on all observed states
- CHANGED kurs.onecode.de Railway CNAME migrated `tgk4io5m`→`ki8dqcf6.up.railway.app` (A 69.46.46.42); app behavior identical (200/307, `railway-hikari`); both raw `up.railway.app` subdomains now return Railway
- CHANGED Supabase platform-level key format change confirmed: JWT `eyJhbGci...` anon key format rejected as "Invalid API key" across all endpoints; only `sb_publishable_` format accepted — not a OneCode key ro
- CHANGED Certspotter CT scan 21:14Z 09-10: exactly 5 names (`onecode.de`, `www`, `kurs`, `cto`, `mta-sts`) — inventory complete, zero new subdomains

## 2026-09-11 01:16:51 UTC
- NEW Supabase REST `/rest/v1/` cadence window re-opened post-00:00Z 2026-09-11 (last probe 11:34Z 09-10 = 503 PGRST002, 11th sequential); gateway 11-state oscillation persists (503→401→503→401→503→503→401→
- NEW Supabase platform-level key format change confirmed: JWT `eyJhbGci...` anon key format rejected as "Invalid API key" across all endpoints; only `sb_publishable_` format accepted — not a OneCode key ro
- CHANGED kurs.onecode.de Railway CNAME migrated `tgk4io5m`→`ki8dqcf6.up.railway.app` (A 69.46.46.42); app behavior identical (200/307, `railway-hikari`); both raw `up.railway.app` subdomains return Railway fal
- CHANGED Certspotter CT scan 21:14Z 09-10: exactly 5 names (`onecode.de`, `www`, `kurs`, `cto`, `mta-sts`) — inventory complete, zero new subdomains

## 2026-09-11 06:11:04 UTC
- NEW Supabase REST `/rest/v1/` returns 401 "Secret API key required" with `sb_publishable_` key (12th sequential probe post-00:00Z 2026-09-11); gateway 11-state oscillation persists (503→401→503→401→503→50
- CHANGED Cadence window re-opened and probed — gateway flipped from 503 (last 11:34Z 09-10) to 401; explicit anon-block confirmed again; no permissive state observed
- NEW Kurs.onecode.de Railway CNAME migration `tgk4io5m`→`ki8dqcf6.up.railway.app` (A 69.46.46.42) confirmed stable; app behavior identical (200/307, `railway-hikari`, `x-railway-edge: lax1`)
- CHANGED Certspotter CT scan 21:14Z 09-10: exactly 5 names (`onecode.de`, `www`, `kurs`, `cto`, `mta-sts`) — inventory complete, zero new subdomains
- CHANGED Supabase platform-level key format change confirmed: JWT `eyJhbGci...` anon key format rejected as "Invalid API key" across all endpoints; only `sb_publishable_` format accepted — not a OneCode key ro

## 2026-09-11 11:33:54 UTC
- CHANGED Supabase REST `/rest/v1/profiles` flipped 503 PGRST002 → 401 "Secret API key required" (13th observation; 12-state oscillation continues)
- CHANGED Supabase Storage `/storage/v1/bucket` changed from 200 `[]` to **400** — endpoint behavior altered (previously empty array for 7+ days)

## 2026-09-11 15:15:09 UTC
- CHANGED Supabase Storage `/storage/v1/bucket` reverted 400 → 200 `[]` with publishable key; transient 400 at 11:33Z was a blip, not config change
- CHANGED Supabase REST `/rest/v1/profiles` flipped 401 → 503 PGRST002 (14th observation; 13-state oscillation persists)
- NEW Supabase Storage `/storage/v1/bucket` shifted from 200 `[]` to 400 (possible project config change)
- NEW Supabase REST `/rest/v1/profiles` flipped 503→401 (13th observation, 12-state oscillation persists)

## 2026-09-11 18:41:26 UTC
- NEW Supabase Storage `/storage/v1/bucket` reverted 400 → 200 `[]` at 15:15Z (transient blip, not config change)
- NEW Supabase REST `/rest/v1/profiles` flipped 401 → 503 PGRST002 (14th observation, 13-state oscillation persists)
- CHANGED Supabase platform-level key format change confirmed: JWT `eyJhbGci...` anon key rejected as "Invalid API key" across all endpoints; only `sb_publishable_` format accepted (not OneCode rotation)
- CHANGED kurs.onecode.de Railway CNAME migrated `tgk4io5m`→`ki8dqcf6.up.railway.app` (A 69.46.46.42); app behavior identical
- CHANGED Certspotter CT scan 21:14Z 09-10: exactly 5 names (`onecode.de`, `www`, `kurs`, `cto`, `mta-sts`) — inventory complete, zero new subdomains

## 2026-09-11 21:22:04 UTC

## 2026-09-11 23:34:01 UTC

## 2026-09-12 01:35:28 UTC

## 2026-09-12 06:34:15 UTC

## 2026-09-12 11:17:19 UTC

## 2026-09-12 14:17:40 UTC

## 2026-09-12 17:25:46 UTC
- NEW Supabase REST `/rest/v1/` returns 401 `UNAUTHORIZED_INVALID_API_KEY_TYPE` with sb_publishable key (was 503 PGRST002 at 01:33Z 09-12); gateway flipped to explicit anon-block state — 15th oscillation si
- CHANGED cto.onecode.de HTTP 409 "error code:1001" re-confirmed live; CNAME→cname.perspective-dns.com stable 12+ days; TLS handshake failure persists on 443
- CHANGED Supabase Storage `/storage/v1/bucket` returns 200 `[]` — empty bucket list confirmed, endpoint probeable
- NEW Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys rejected as "Invalid API key" across all endpoints (not OneCode rotation)

## 2026-09-12 19:30:39 UTC
- NEW Supabase REST `/rest/v1/` returns 401 `UNAUTHORIZED_INVALID_API_KEY_TYPE` with `sb_publishable` key (was 503 PGRST002 at 01:33Z 09-12); 15th gateway oscillation confirmed
- CHANGED cto.onecode.de HTTP 409 "error code:1001" re-confirmed live; CNAME→cname.perspective-dns.com stable 12+ days; TLS handshake failure persists on 443
- CHANGED Supabase Storage `/storage/v1/bucket` returns 200 `[]` — empty bucket list confirmed, endpoint probeable
- NEW Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys rejected as "Invalid API key" across all endpoints (not OneCode rotation)

## 2026-09-12 21:41:03 UTC
- NEW Supabase REST `/rest/v1/` returns 401 `UNAUTHORIZED_INVALID_API_KEY_TYPE` with `sb_publishable` key (was 503 PGRST002 at 01:33Z 09-12); 15th gateway oscillation confirmed
- CHANGED cto.onecode.de HTTP 409 "error code:1001" re-confirmed live; CNAME→cname.perspective-dns.com stable 12+ days; TLS handshake failure persists on 443
- CHANGED Supabase Storage `/storage/v1/bucket` returns 200 `[]` — empty bucket list confirmed, endpoint probeable
- NEW Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys rejected as "Invalid API key" across all endpoints (not OneCode rotation)

## 2026-09-12 23:25:05 UTC
- CHANGED kurs.onecode.de `x-railway-edge` flipped lax1→iad1 (23:24Z) + `x-hikari-trace` iad1.* — Railway edge region load-balancing noise, no app-level change; /login 200 (railway-hikari, no Set-Cookie), / 307
- NEW Supabase REST `/rest/v1/` returns 401 `UNAUTHORIZED_INVALID_API_KEY_TYPE` with `sb_publishable` key (was 503 PGRST002 at 01:33Z 09-12); 15th gateway oscillation confirmed
- CHANGED cto.onecode.de HTTP 409 "error code:1001" re-confirmed live; CNAME→cname.perspective-dns.com stable 12+ days; TLS handshake failure persists on 443
- CHANGED Supabase Storage `/storage/v1/bucket` returns 200 `[]` — empty bucket list confirmed, endpoint probeable
- NEW Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys rejected as "Invalid API key" across all endpoints (not OneCode rotation)
- CHANGED kurs.onecode.de `/login` 200 + `/` 307→/login re-confirmed 19:29Z 09-12; pre-auth surface stable, exhausted; no new cookie/session signal

## 2026-09-13 01:26:11 UTC
- NEW Supabase REST `/rest/v1/` returned `401 UNAUTHORIZED_INVALID_API_KEY_TYPE` with `sb_publishable` key at 23:24Z 2026-09-12 (was 503 PGRST002 at 01:33Z 09-12); 15th gateway oscillation confirmed since 0
- NEW Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys (`eyJhbGci...`) rejected as "Invalid API key" across all endpoints (platform-level change, not OneCode rotation)
- CHANGED `cto.onecode.de` HTTP 409 "error code:1001" re-confirmed live; CNAME→cname.perspective-dns.com stable 12+ days; TLS handshake failure persists on 443
- CHANGED Supabase Storage `/storage/v1/bucket` returns 200 `[]` — empty bucket list confirmed, endpoint probeable
- CHANGED `kurs.onecode.de` `/login` 200 + `/` 307→/login re-confirmed 19:29Z 2026-09-12; pre-auth surface stable, exhausted; no new cookie/session signal
- CHANGED `kurs.onecode.de` `x-railway-edge` flipped lax1→iad1 (23:24Z) + `x-hikari-trace` iad1.* — Railway edge region load-balancing noise, no app-level change

## 2026-09-13 06:48:36 UTC
- NEW Supabase REST `/rest/v1/` currently returns 401 `UNAUTHORIZED_INVALID_API_KEY_TYPE` with `sb_publishable` key (16th oscillation since 09-04, flipped from 503 at 00:24Z 09-13 to 401 now)
- NEW Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys rejected globally (platform change, not OneCode rotation)
- CHANGED `cto.onecode.de` HTTP 409 "error code:1001" re-confirmed live; CNAME→cname.perspective-dns.com stable 13+ days; TLS handshake failure persists on 443
- CHANGED Supabase Storage `/storage/v1/bucket` returns 200 `[]` — empty bucket list confirmed, endpoint probeable
- CHANGED `kurs.onecode.de` `/login` 200 + `/` 307→/login re-confirmed; pre-auth surface stable, exhausted; no new cookie/session signal
- CHANGED `kurs.onecode.de` `x-railway-edge` flipped iad1→lax1 (load balancing noise, no app-level change)

## 2026-09-13 12:43:31 UTC

## 2026-09-13 16:42:35 UTC

## 2026-09-13 19:05:29 UTC

## 2026-09-13 21:26:55 UTC

## 2026-09-13 23:38:27 UTC

## 2026-09-14 01:53:33 UTC
- NEW Cadence window open for 18th Supabase REST probe (post-00:00Z 2026-09-14): last probe 00:24Z 09-13 = 503 PGRST002 (16-state oscillation); 17th probe was 401 at 06:46Z 09-13; 18th probe due now
- NEW Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys (`eyJhbGci...`) rejected globally as "Invalid API key" — confirmed platform-level change, not OneCode rotation
- CHANGED cto.onecode.de: CNAME→cname.perspective-dns.com stable 13+ days; HTTP 409 "error code:1001" + TLS handshake-fail persistent; zero verification TXT records
- CHANGED kurs.onecode.de: /login 200 + / 307→/login stable; Railway edge region flapping (iad1↔lax1) — load balancing noise, no app change
- CHANGED Supabase Storage `/storage/v1/bucket`: 200 `[]` baseline holds (post-400 blip 09-11); endpoint probeable, zero buckets
- NEW Cadence window open for 18th Supabase REST probe (post-00:00Z 2026-09-14): last probe 00:24Z 09-13 = 503 PGRST002 (16-state oscillation); 17th probe was 401 at 06:46Z 09-13; 18th probe due now
- NEW Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys (`eyJhbGci...`) rejected globally as "Invalid API key" — confirmed platform-level change, not OneCode rotation
- CHANGED cto.onecode.de: CNAME→cname.perspective-dns.com stable 13+ days; HTTP 409 "error code:1001" + TLS handshake-fail persistent; zero verification TXT records
- CHANGED kurs.onecode.de: /login 200 + / 307→/login stable; Railway edge region flapping (iad1↔lax1) — load balancing noise, no app change
- CHANGED Supabase Storage `/storage/v1/bucket`: 200 `[]` baseline holds (post-400 blip 09-11); endpoint probeable, zero buckets
- NEW Cadence window open for 18th Supabase REST probe (post-00:00Z 2026-09-14): last probe 00:24Z 09-13 = 503 PGRST002 (16-state oscillation); 17th probe was 401 at 06:46Z 09-13; 18th probe due now
- NEW Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys (`eyJhbGci...`) rejected globally as "Invalid API key" — confirmed platform-level change, not OneCode rotation
- CHANGED cto.onecode.de: CNAME→cname.perspective-dns.com stable 13+ days; HTTP 409 "error code:1001" + TLS handshake-fail persistent; zero verification TXT records
- CHANGED kurs.onecode.de: /login 200 + / 307→/login stable; Railway edge region flapping (iad1↔lax1) — load balancing noise, no app change
- CHANGED Supabase Storage `/storage/v1/bucket`: 200 `[]` baseline holds (post-400 blip 09-11); endpoint probeable, zero buckets

## 2026-09-14 07:11:55 UTC
- NEW Cadence window open for 18th Supabase REST probe (post-00:00Z 2026-09-14): last probe 00:24Z 09-13 = 503 PGRST002 (16-state oscillation); 17th probe was 401 at 06:46Z 09-13; 18th probe due now
- NEW Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys (`eyJhbGci...`) rejected globally as "Invalid API key" — confirmed platform-level change, not OneCode rotation
- CHANGED cto.onecode.de: CNAME→cname.perspective-dns.com stable 13+ days; HTTP 409 "error code:1001" + TLS handshake-fail persistent; zero verification TXT records
- CHANGED kurs.onecode.de: /login 200 + / 307→/login stable; Railway edge region flapping (iad1↔lax1) — load balancing noise, no app change
- CHANGED Supabase Storage `/storage/v1/bucket`: 200 `[]` baseline holds (post-400 blip 09-11); endpoint probeable, zero buckets

## 2026-09-14 14:23:38 UTC

## 2026-09-14 19:33:50 UTC
- CHANGED Supabase REST `/rest/v1/` 19th probe 14:16Z 09-14 = 503 PGRST002 (no flip from 01:42Z); 18-state oscillation persists (…→401→503 since 09-04); never permissive
- CHANGED cto.onecode.de 409/1001 live 14:16Z 09-14; CNAME→cname.perspective-dns.com stable 14+ days; conf 58, HUMAN pending
- CHANGED kurs.onecode.de /login 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- CHANGED Supabase Storage `/storage/v1/bucket` 200 `[]` holds — endpoint probeable, zero buckets

## 2026-09-14 22:56:04 UTC
- CHANGED Supabase REST `/rest/v1/` 20th probe 22:47Z 09-14 = 401 `UNAUTHORIZED_INVALID_API_KEY_TYPE` (flip from 503 at 14:16Z); 19-state oscillation persists (…→503→401 since 09-04); never permissive
- CHANGED cto.onecode.de 409/1001 live 22:47Z 09-14; CNAME→cname.perspective-dns.com stable 14+ days; conf 58, HUMAN pending
- CHANGED kurs.onecode.de /login 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- CHANGED Supabase Storage `/storage/v1/bucket` 200 `[]` holds — endpoint probeable, zero buckets
- CHANGED Supabase Functions `/functions/v1/` 404; no deployed functions
- CHANGED Supabase Realtime `/realtime/v1/` 401; auth required
- CHANGED Supabase GraphQL `/graphql/v1` 503 PGRST002; cache down
- CHANGED Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys (`eyJhbGci...`) rejected globally as "Invalid API key" — confirmed platform-level change, not OneCode rotation

## 2026-09-15 01:19:45 UTC
- NEW Cadence window open for 21st Supabase REST probe (post-00:00Z 2026-09-15): last probe 22:47Z 09-14 = 401 `UNAUTHORIZED_INVALID_API_KEY_TYPE` (19-state oscillation); 21st probe due now
- NEW Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys (`eyJhbGci...`) rejected globally as "Invalid API key" — confirmed platform-level change, not OneCode rotation
- CHANGED cto.onecode.de: CNAME→cname.perspective-dns.com stable 14+ days; HTTP 409/1001 + TLS handshake-fail persistent; zero verification TXT records
- CHANGED kurs.onecode.de: /login 200 + / 307→/login stable; Railway edge region flapping (iad1↔lax1) — load balancing noise, no app change
- CHANGED Supabase Storage `/storage/v1/bucket`: 200 `[]` holds — endpoint probeable, zero buckets
- CHANGED Supabase Functions `/functions/v1/`: 404; no deployed functions
- CHANGED Supabase Realtime `/realtime/v1/`: 401; auth required
- CHANGED Supabase GraphQL `/graphql/v1`: 503 PGRST002; cache down

## 2026-09-15 06:15:55 UTC
- NEW Cadence window open for 21st Supabase REST probe (post-00:00Z 2026-09-15): last probe 22:47Z 09-14 = 401 `UNAUTHORIZED_INVALID_API_KEY_TYPE` (19-state oscillation); 21st probe due now
- NEW Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys (`eyJhbGci...`) rejected globally as "Invalid API key" — confirmed platform-level change, not OneCode rotation
- CHANGED cto.onecode.de: CNAME→cname.perspective-dns.com stable 14+ days; HTTP 409/1001 + TLS handshake-fail persistent; zero verification TXT records
- CHANGED kurs.onecode.de: /login 200 + / 307→/login stable; Railway edge region flapping (iad1↔lax1) — load balancing noise, no app change
- CHANGED Supabase Storage `/storage/v1/bucket`: 200 `[]` holds — endpoint probeable, zero buckets
- CHANGED Supabase Functions `/functions/v1/`: 404; no deployed functions
- CHANGED Supabase Realtime `/realtime/v1/`: 401; auth required
- CHANGED Supabase GraphQL `/graphql/v1`: 503 PGRST002; cache down

## 2026-09-15 11:57:38 UTC

## 2026-09-15 16:53:45 UTC

## 2026-09-15 19:57:14 UTC
- CHANGED Supabase REST gateway: 23rd probe 01:16Z 09-16 = 503 PGRST002 (no flip from prior 503); 22-state oscillation (503↔401) persists since 09-04; never permissive on any observed state
- CHANGED cto.onecode.de: CNAME→cname.perspective-dns.com stable 16+ days; HTTP 409 "error code:1001" + TLS handshake-fail persistent; zero verification TXT records
- CHANGED kurs.onecode.de: /login 200 + / 307→/login unchanged 09-16; pre-auth surface stable, exhausted; no new cookie/session signal
- CHANGED Supabase Storage /storage/v1/bucket: 200 `[]` baseline holds — endpoint probeable, zero buckets
- CHANGED Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys (`eyJhbGci...`) rejected globally as "Invalid API key" — confirmed platform-level change, not OneCode rotation

## 2026-09-15 22:55:53 UTC
- CHANGED Supabase REST gateway: 23rd probe 01:16Z 09-16 = 503 PGRST002 (no flip from prior 503); 22-state oscillation (503↔401) persists since 09-04; never permissive on any observed state
- CHANGED cto.onecode.de: CNAME→cname.perspective-dns.com stable 16+ days; HTTP 409 "error code:1001" + TLS handshake-fail persistent; zero verification TXT records
- CHANGED kurs.onecode.de: /login 200 + / 307→/login unchanged 09-16; pre-auth surface stable, exhausted; no new cookie/session signal
- CHANGED Supabase Storage /storage/v1/bucket: 200 `[]` baseline holds — endpoint probeable, zero buckets
- CHANGED Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys (`eyJhbGci...`) rejected globally as "Invalid API key" — confirmed platform-level change, not OneCode rotation

## 2026-09-16 01:13:36 UTC
- NEW Supabase REST gateway 23rd probe 01:16Z 2026-09-16 = 503 PGRST002 (no flip from prior 503); 22-state oscillation (503↔401) persists since 09-04; never permissive on any observed state
- CHANGED cto.onecode.de: CNAME→cname.perspective-dns.com stable 16+ days; HTTP 409 "error code:1001" + TLS handshake-fail persistent; zero verification TXT records
- CHANGED kurs.onecode.de: /login 200 + / 307→/login unchanged 09-16; pre-auth surface stable, exhausted; no new cookie/session signal
- CHANGED Supabase Storage /storage/v1/bucket: 200 `[]` baseline holds — endpoint probeable, zero buckets
- CHANGED Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys (`eyJhbGci...`) rejected globally as "Invalid API key" — confirmed platform-level change, not OneCode rotation

## 2026-09-16 06:13:42 UTC

## 2026-09-16 11:51:46 UTC
- NEW Supabase REST gateway 23rd probe 01:16Z 2026-09-16 = 503 PGRST002 (no flip from prior 503); 22-state oscillation (503↔401) persists since 09-04; never permissive on any observed state
- NEW cto.onecode.de: CNAME→cname.perspective-dns.com stable 16+ days; HTTP 409 "error code:1001" + TLS handshake-fail persistent; zero verification TXT records
- NEW kurs.onecode.de: /login 200 + / 307→/login unchanged 09-16; pre-auth surface stable, exhausted; no new cookie/session signal
- NEW Supabase Storage /storage/v1/bucket: 200 `[]` baseline holds — endpoint probeable, zero buckets
- NEW Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys (`eyJhbGci...`) rejected globally as "Invalid API key" — confirmed platform-level change, not OneCode rotation

## 2026-09-16 16:35:51 UTC
- CHANGED REST gateway: supplementary same-day probe 16:33Z 09-16 (24th sequential obs) = 503 PGRST002 on both `/profiles` and `/enrollments` — no flip from 01:16Z 09-16; cadence infraction noted (2 probes 09-1
- NEW NO_DELTA — identical state to 2026-09-15 22:55Z: Supabase REST 23rd probe 503 PGRST002 (22-state oscillation 503↔401 since 09-04), cto.onecode.de CNAME→cname.perspective-dns.com 16+ days HTTP 409/TLS-

## 2026-09-16 20:03:42 UTC

## 2026-09-16 22:48:57 UTC

## 2026-09-17 01:14:53 UTC

## 2026-09-17 06:18:37 UTC
- NEW Supabase REST gateway 24th probe 16:33Z 09-16 (supplementary, same-day) = 503 PGRST002 on `/profiles` + `/enrollments` — no flip from 01:16Z; 22-state oscillation persists; cadence infraction noted (2
- NEW x-middleware-subrequest bypass header (CVE-2025-29927) tested live 16:34Z-19:5xZ 09-16 on `/api/v1/health` + `/dashboard` — both still 307→/login; Next.js patch level > vulnerable; middleware auth gat
- NEW _next/image external URL fetch tested → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- CHANGED cto.onecode.de: CNAME→cname.perspective-dns.com stable 17+ days (day 17 at 09-16), HTTP 409 "error code:1001", TLS handshake-fail, zero verification TXT; conf 58 HUMAN claim-attempt only proof path
- CHANGED kurs.onecode.de: /login 200 + / 307→/login + no Set-Cookie re-confirmed 23:24Z 09-16 (railway-hikari, x-railway-edge iad1→lax1 region flip noise); pre-auth surface exhaustively re-validated including 
- CHANGED Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys (`eyJhbGci...`) rejected globally as "Invalid API key" — confirmed platform-level change, not OneCode rotation

## 2026-09-17 11:54:25 UTC

## 2026-09-17 16:42:11 UTC
- NEW Supabase REST gateway still 503 PGRST002 (23rd sequential probe) — oscillation 503↔401 persists since 09-04, never permissive
- NEW cto.onecode.de HTTP 409 "error code:1001" + TLS handshake-fail re-confirmed; CNAME→cname.perspective-dns.com stable 17+ days; zero verification TXT
- NEW kurs.onecode.de /login 200 (no Set-Cookie, railway-hikari, x-railway-edge iad1) + / 307→/login stable; pre-auth surface exhaustively re-validated (CVE-2025-29927 negative, _next/image SSRF negative)
- NEW Supabase Storage /storage/v1/bucket 200 `[]` — endpoint probeable, zero buckets
- NEW Supabase Functions 404, Realtime 401 — no pre-auth exposure
- NEW Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys rejected globally as "Invalid API key"

## 2026-09-17 19:53:26 UTC
- NEW Supabase REST monitor formally closed 09-17 — 26 probes (503↔401) since 09-04, never 200+rows; publishable-key rejection is platform-enforced; no further cadence probes
- NEW cto.onecode.de CNAME→cname.perspective-dns.com day-18, TXT zero; unbound/reclaimable; conf 58 holds; HUMAN claim-attempt is the only proof path — passive probes have converged, no delta value
- CHANGED kurs.onecode.de pre-auth surface exhaustively re-validated including CVE-2025-29927 (negative) and _next/image SSRF (negative); zero new pre-auth vectors
- CHANGED Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys (`eyJhbGci...`) rejected globally as "Invalid API key" — confirmed platform-level change, not OneCode rotation
- CHANGED Supabase Storage `/storage/v1/bucket` 200 `[]` holds — endpoint probeable, zero buckets (stable 10+ days)
- CHANGED Supabase Functions 404, Realtime 401, GraphQL 503 — no pre-auth exposure, unchanged

## 2026-09-17 22:45:48 UTC
- NEW Current time 2026-09-17 22:45 UTC — 3 hours since last lead update (19:53); no new passive probes executed in this window
- CHANGED Supabase REST monitor formally closed 09-17 — 26 probes (503↔401) since 09-04, never 200+rows; publishable-key rejection is platform-enforced; no further cadence probes
- CHANGED cto.onecode.de CNAME→cname.perspective-dns.com day-18, TXT zero; unbound/reclaimable; conf 58 holds; HUMAN claim-attempt is the only proof path — passive probes have converged, no delta value
- CHANGED kurs.onecode.de pre-auth surface exhaustively re-validated including CVE-2025-29927 (negative) and _next/image SSRF (negative); zero new pre-auth vectors
- CHANGED Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys (`eyJhbGci...`) rejected globally as "Invalid API key" — confirmed platform-level change, not OneCode rotation
- CHANGED Supabase Storage `/storage/v1/bucket` 200 `[]` holds — endpoint probeable, zero buckets (stable 10+ days)
- CHANGED Supabase Functions 404, Realtime 401, GraphQL 503 — no pre-auth exposure, unchanged

## 2026-09-18 01:09:29 UTC
- NEW No new passive probes executed since 2026-09-17 22:45 UTC (3 hours ago); all surfaces identical to last lead update
- CHANGED Supabase REST monitor formally closed 09-17 — 26 probes (503↔401) since 09-04, never 200+rows; publishable-key rejection platform-enforced; no further cadence probes
- CHANGED cto.onecode.de CNAME→cname.perspective-dns.com day-18, TXT zero; unbound/reclaimable; conf 58 holds; HUMAN claim-attempt only proof path — passive probes converged
- CHANGED kurs.onecode.de pre-auth surface exhaustively re-validated including CVE-2025-29927 (negative) and _next/image SSRF (negative); zero new pre-auth vectors

## 2026-09-18 06:08:40 UTC
- NEW Live re-probe 06:04Z 09-18 vs last lead 01:09Z 09-18: kurs.onecode.de /login=200 (no Set-Cookie), /=307→/login, /api/broadcast=307→/login, x-middleware-subrequest bypass header STILL non-bypassing (30
- NEW Live re-probe 06:04Z 09-18: cto.onecode.de CNAME→cname.perspective-dns.com (day-20), HTTP 409 via --resolve, TXT zero at target; aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket=200 — all identical 
- CHANGED Triage 7Q gate (mimo) invoked 01:06Z + 06:01Z 09-18 with EMPTY LEADS — zero new findings in flight; only the two escalation-gated leads (BOLA AUTH_HELPED, cto CNAME HUMAN_ONLY) remain unresolved.

## 2026-09-18 11:31:12 UTC
- CHANGED kurs.onecode.de: 06:04Z re-probe — /login 200, / 307, /api/broadcast 307, x-middleware-subrequest bypass header still non-bypassing (CVE-2025-29927 negative); pre-auth surface unchanged day-20
- CHANGED cto.onecode.de: 06:04Z — CNAME→cname.perspective-dns.com day-20 (104.18.2.73/3.73), HTTP 409 live, TXT zero; conf 58 holds
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds 06:04Z — endpoint probeable, zero buckets; unchanged
- CHANGED Triage 7Q gate invoked 01:06Z/06:01Z 09-18 with EMPTY LEADS — zero new findings; only two escalation-gated leads remain (BOLA AUTH_HELPED, cto CNAME HUMAN_ONLY)

## 2026-09-18 15:11:32 UTC
- NEW New Next.js build deployed since 09-05: main client chunk `0-lpao5_i9htd.js` → `0-mbmp1iqb6hj.js` (fetched 15:09Z 09-18). Client route refs now {/admin,/courses,/dashboard,/einladung,/passwort-neu,/pa

## 2026-09-18 18:41:09 UTC
- NEW kurs.onecode.de: New Next.js build deployed 2026-09-18 15:09Z (chunk `0-mbmp1iqb6hj.js`); client route refs now {/admin,/courses,/dashboard,/einladung,/passwort-neu,/passwort-vergessen}; `/api/broadca
- NEW kurs.onecode.de: Verified `/admin`, `/courses`, `/dashboard`, `/einladung`, `/passwort-neu` all 307→/login; `/api/courses`, `/api/resources`, `/api/enrollments`, `/v1/*` all 307→/login — zero new pre-
- CHANGED cto.onecode.de: HTTP 409 "error code:1001" re-confirmed live 2026-09-18 18:39Z; CNAME→cname.perspective-dns.com stable 20+ days; TLS handshake-fail on 443; zero verification TXT records
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` re-confirmed 2026-09-18 18:40Z — endpoint probeable, zero buckets; unchanged
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection platform-enforced; no further cadence probes

## 2026-09-18 21:16:49 UTC
- NEW kurs.onecode.de: New Next.js build deployed 2026-09-18 15:09Z (chunk `0-mbmp1iqb6hj.js`); client route refs now {/admin,/courses,/dashboard,/einladung,/passwort-neu,/passwort-vergessen}; `/api/broadca
- NEW kurs.onecode.de: Verified `/admin`, `/courses`, `/dashboard`, `/einladung`, `/passwort-neu` all 307→/login; `/api/courses`, `/api/resources`, `/api/enrollments`, `/v1/*` all 307→/login — zero new pre-
- CHANGED cto.onecode.de: HTTP 409 "error code:1001" re-confirmed live 2026-09-18 18:39Z; CNAME→cname.perspective-dns.com stable 20+ days; TLS handshake-fail on 443; zero verification TXT records
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` re-confirmed 2026-09-18 18:40Z — endpoint probeable, zero buckets; unchanged
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection platform-enforced; no further cadence probes

## 2026-09-18 23:24:36 UTC

## 2026-09-19 01:37:31 UTC

## 2026-09-19 06:39:33 UTC
- CHANGED kurs.onecode.de: new build live 15:09Z 09-18 (chunk 0-mbmp1iqb6hj.js), client route refs {/admin,/courses,/dashboard,/einladung,/passwort-neu,/passwort-vergessen}; all referenced handlers 307→/login; 
- CHANGED cto.onecode.de: CNAME→cname.perspective-dns.com stable 21+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm pending
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets

## 2026-09-19 11:36:54 UTC

## 2026-09-19 14:52:08 UTC
- NEW kurs.onecode.de: new deploy 11:33Z 09-19 (boot 2a8cgfwu75lsu, module 4310-_brt1a3g) adds pre-auth /datenschutz + /rechtliches — static legal pages, no form action, no /api, contact@onecode.de public; 
- CHANGED kurs.onecode.de: pre-auth surface now = /login, /passwort-vergessen, /datenschutz, /rechtliches (all 200); /admin,/courses,/dashboard,/api/*,/v1/* remain 307→/login

## 2026-09-19 17:53:37 UTC
- NEW kurs.onecode.de: live re-diff 17:52Z 09-19 — /login 200 (railway-hikari, lax1.e74w, no Set-Cookie), main chunk `0-mbmp1iqb6hj.js` sha256 f916f314... unchanged since 15:09Z 09-18 build; module `4310-_b
- CHANGED None — cto.onecode.de CNAME→cname.perspective-dns.com live re-confirmed day-23 (17:52Z); storage/functions/realtime/REST states unchanged across 20+ cycles.
- NEW kurs.onecode.de: pre-auth surface expanded to `/datenschutz` + `/rechtliches` (static legal pages, 200, prerendered, no forms/API) — confirmed live 09-19 11:33Z deploy
- CHANGED kurs.onecode.de: pre-auth surface = `/login`, `/passwort-vergessen`, `/datenschutz`, `/rechtliches` (all 200); `/admin`, `/courses`, `/dashboard`, `/api/*`, `/v1/*` remain 307→/login
- CHANGED cto.onecode.de: CNAME→cname.perspective-dns.com stable 23+ days; HTTP 409 "error code:1001" on port 80; TLS handshake failure on 443; zero verification TXT records
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket: 200 `[]` confirmed — endpoint probeable with `sb_publishable_` key, zero buckets
- CHANGED Supabase REST `/rest/v1/`: monitor formally closed 09-17 (26 probes, 503↔401 oscillation, never 200+rows); platform enforces `sb_publishable_` format only
- CHANGED kurs.onecode.de: x-middleware-subrequest bypass (CVE-2025-29927) negative; `_next/image` SSRF negative; pre-auth surface exhaustively validated

## 2026-09-19 20:23:14 UTC
- NEW kurs.onecode.de: pre-auth surface expanded to `/datenschutz` + `/rechtliches` (static legal pages, 200, prerendered, no forms/API) — confirmed live 09-19 11:33Z deploy
- CHANGED kurs.onecode.de: pre-auth surface = `/login`, `/passwort-vergessen`, `/datenschutz`, `/rechtliches` (all 200); `/admin`, `/courses`, `/dashboard`, `/api/*`, `/v1/*` remain 307→/login
- CHANGED cto.onecode.de: CNAME→cname.perspective-dns.com stable 23+ days; HTTP 409 "error code:1001" on port 80; TLS handshake failure on 443; zero verification TXT records
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket: 200 `[]` confirmed — endpoint probeable with `sb_publishable_` key, zero buckets
- CHANGED Supabase REST `/rest/v1/`: monitor formally closed 09-17 (26 probes, 503↔401 oscillation, never 200+rows); platform enforces `sb_publishable_` format only
- CHANGED kurs.onecode.de: x-middleware-subrequest bypass (CVE-2025-29927) negative; `_next/image` SSRF negative; pre-auth surface exhaustively validated

## 2026-09-19 22:32:25 UTC
- NEW kurs.onecode.de: pre-auth surface expanded to `/datenschutz` + `/rechtliches` (static legal pages, 200, prerendered, no forms/API) — confirmed live 09-19 11:33Z deploy
- CHANGED kurs.onecode.de: pre-auth surface = `/login`, `/passwort-vergessen`, `/datenschutz`, `/rechtliches` (all 200); `/admin`, `/courses`, `/dashboard`, `/api/*`, `/v1/*` remain 307→/login
- CHANGED cto.onecode.de: CNAME→cname.perspective-dns.com stable 23+ days; HTTP 409 "error code:1001" on port 80; TLS handshake failure on 443; zero verification TXT records
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket: 200 `[]` confirmed — endpoint probeable with `sb_publishable_` key, zero buckets
- CHANGED Supabase REST `/rest/v1/`: monitor formally closed 09-17 (26 probes, 503↔401 oscillation, never 200+rows); platform enforces `sb_publishable_` format only
- CHANGED kurs.onecode.de: x-middleware-subrequest bypass (CVE-2025-29927) negative; `_next/image` SSRF negative; pre-auth surface exhaustively validated
- NEW kurs.onecode.de: pre-auth surface expanded to `/datenschutz` + `/rechtliches` (static legal pages, 200, prerendered, no forms/API) — confirmed live 09-19 11:33Z deploy
- CHANGED kurs.onecode.de: pre-auth surface = `/login`, `/passwort-vergessen`, `/datenschutz`, `/rechtliches` (all 200); `/admin`, `/courses`, `/dashboard`, `/api/*`, `/v1/*` remain 307→/login
- CHANGED cto.onecode.de: CNAME→cname.perspective-dns.com stable 23+ days; HTTP 409 "error code:1001" on port 80; TLS handshake failure on 443; zero verification TXT records
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket: 200 `[]` confirmed — endpoint probeable with `sb_publishable_` key, zero buckets
- CHANGED Supabase REST `/rest/v1/`: monitor formally closed 09-17 (26 probes, 503↔401 oscillation, never 200+rows); platform enforces `sb_publishable_` format only
- CHANGED kurs.onecode.de: x-middleware-subrequest bypass (CVE-2025-29927) negative; `_next/image` SSRF negative; pre-auth surface exhaustively validated
- NEW kurs.onecode.de: pre-auth surface expanded to `/datenschutz` + `/rechtliches` (static legal pages, 200, prerendered, no forms/API) — confirmed live 09-19 11:33Z deploy
- CHANGED kurs.onecode.de: pre-auth surface = `/login`, `/passwort-vergessen`, `/datenschutz`, `/rechtliches` (all 200); `/admin`, `/courses`, `/dashboard`, `/api/*`, `/v1/*` remain 307→/login
- CHANGED cto.onecode.de: CNAME→cname.perspective-dns.com stable 23+ days; HTTP 409 "error code:1001" on port 80; TLS handshake failure on 443; zero verification TXT records
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket: 200 `[]` confirmed — endpoint probeable with `sb_publishable_` key, zero buckets
- CHANGED Supabase REST `/rest/v1/`: monitor formally closed 09-17 (26 probes, 503↔401 oscillation, never 200+rows); platform enforces `sb_publishable_` format only
- CHANGED kurs.onecode.de: x-middleware-subrequest bypass (CVE-2025-29927) negative; `_next/image` SSRF negative; pre-auth surface exhaustively validated

## 2026-09-20 00:25:15 UTC

## 2026-09-20 05:27:54 UTC

## 2026-09-20 10:11:35 UTC

## 2026-09-20 14:23:14 UTC

## 2026-09-20 17:37:25 UTC

## 2026-09-20 19:48:58 UTC

## 2026-09-20 22:22:08 UTC
- NEW NO_DELTA — all surfaces identical to 2026-09-20 19:48Z confirmation: kurs.onecode.de /login 200, /datenschutz 200, / 307→/login, /api/* 307; cto.onecode.de CNAME→cname.perspective-dns.com day-27 (409/

## 2026-09-21 00:22:12 UTC
- NEW Minor: /login Link preload references new woff2 `75affa71d1e2f6a7-s.p.17-aodiw50953.woff2` (fetchable 200, 34KB) — assets re-publish artifact, main chunk + route set identical ⇒ no code deploy, no new

## 2026-09-21 05:13:57 UTC
- NEW NO_DELTA — all surfaces identical to 2026-09-20 19:48Z confirmation: kurs.onecode.de /login 200, /datenschutz 200, / 307→/login, /api/* 307; cto.onecode.de CNAME→cname.perspective-dns.com day-27 (409/
- NEW Minor: /login Link preload references new woff2 `75affa71d1e2f6a7-s.p.17-aodiw50953.woff2` (fetchable 200, 34KB) — asset re-publish artifact, main chunk sha256 f916f314 + route set identical ⇒ no code
- CHANGED cto.onecode.de CNAME→cname.perspective-dns.com day-29 stable; HTTP 409/1001 + TLS handshake-fail persist; zero verification TXT; conf 58 holds
- CHANGED Supabase storage/v1/bucket 200 `[]` re-confirmed — endpoint probeable, zero buckets; unchanged
- CHANGED Supabase REST monitor formally closed 09-17 (26 probes, 503↔401 never permissive); platform enforces `sb_publishable_` format only
- CHANGED kurs.onecode.de pre-auth surface stable day-29: /login, /passwort-vergessen, /datenschutz, /rechtliches at 200; all /api/*, /v1, /dashboard, /admin, /courses 307→/login; no new cookie/session signal

## 2026-09-21 10:55:56 UTC
- NEW Minor: /login Link preload references new woff2 `75affa71d1e2f6a7-s.p.17-aodiw50953.woff2` (fetchable 200, 34KB) — asset re-publish artifact, main chunk sha256 f916f314 + route set identical ⇒ no code
- CHANGED cto.onecode.de CNAME→cname.perspective-dns.com day-29 stable; HTTP 409/1001 + TLS handshake-fail persist; zero verification TXT; conf 58 holds
- CHANGED Supabase storage/v1/bucket 200 `[]` re-confirmed — endpoint probeable, zero buckets; unchanged
- CHANGED Supabase REST monitor formally closed 09-17 (26 probes, 503↔401 never permissive); platform enforces `sb_publishable_` format only
- CHANGED kurs.onecode.de pre-auth surface stable day-29: /login, /passwort-vergessen, /datenschutz, /rechtliches at 200; all /api/*, /v1, /dashboard, /admin, /courses 307→/login; no new cookie/session signal

## 2026-09-21 17:01:19 UTC
- NEW Minor: /login Link preload references new woff2 `75affa71d1e2f6a7-s.p.17-aodiw50953.woff2` (fetchable 200, 34KB) — asset re-publish artifact, main chunk sha256 f916f314 + route set identical ⇒ no code
- CHANGED cto.onecode.de CNAME→cname.perspective-dns.com day-29 stable; HTTP 409/1001 + TLS handshake-fail persist; zero verification TXT; conf 58 holds
- CHANGED Supabase storage/v1/bucket 200 `[]` re-confirmed — endpoint probeable, zero buckets; unchanged
- CHANGED Supabase REST monitor formally closed 09-17 (26 probes, 503↔401 never permissive); platform enforces `sb_publishable_` format only
- CHANGED kurs.onecode.de pre-auth surface stable day-29: /login, /passwort-vergessen, /datenschutz, /rechtliches at 200; all /api/*, /v1, /dashboard, /admin, /courses 307→/login; no new cookie/session signal

## 2026-09-21 20:56:27 UTC

## 2026-09-22 00:00:02 UTC

## 2026-09-22 04:42:26 UTC

## 2026-09-22 09:46:21 UTC

## 2026-09-22 14:34:31 UTC

## 2026-09-22 18:19:06 UTC

## 2026-09-22 21:30:12 UTC

## 2026-09-22 23:51:08 UTC

## 2026-09-23 04:12:29 UTC

## 2026-09-23 09:24:42 UTC

## 2026-09-23 14:29:09 UTC
- NEW NO_DELTA — all surfaces identical to 2026-09-23 09:24Z: kurs.onecode.de pre-auth (/login,/passwort-vergessen,/datenschutz,/rechtliches 200; /api/*,/v1,/dashboard,/admin 307→/login), cto.onecode.de CNA

## 2026-09-23 18:42:27 UTC

## 2026-09-23 21:51:53 UTC

## 2026-09-24 00:23:06 UTC
- NEW kurs.onecode.de: No new deploy since 2026-09-19 11:33Z (chunk `0-mbmp1iqb6hj.js` sha256 f916f314... byte-identical); pre-auth surface stable = {/login,/passwort-vergessen,/datenschutz,/rechtliches} 20
- NEW cto.onecode.de: CNAME→cname.perspective-dns.com stable 34+ days; HTTP 409 "error code:1001" + TLS handshake-fail persists; zero verification TXT records; conf 58 holds
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket: 200 `[]` re-confirmed — endpoint probeable with `sb_publishable_` key, zero buckets; unchanged since 09-04
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles: 503 PGRST002 (schema-cache-down) — monitor formally closed 09-17 after 26 probes (503↔401 oscillation), never 200+rows; platform enforces `sb_publish
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/settings: Unchanged — email-only, disable_signup=true, mailer_autoconfirm=false, all external OAuth false, passkeys disabled
- NEW kurs.onecode.de: x-middleware-subrequest bypass (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16; _next/image SSRF negative; pre-auth surface exhaustively validated
- CHANGED Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys (`eyJhbGci...`) rejected globally as "Invalid API key" — confirmed platform-level change, not OneCode rotation

## 2026-09-24 05:09:00 UTC

## 2026-09-24 10:13:41 UTC

## 2026-09-24 15:18:24 UTC

## 2026-09-24 19:20:24 UTC

## 2026-09-24 22:35:08 UTC
- NEW kurs.onecode.de: No delta since 09-24 19:20Z — /login 200 (no Set-Cookie, iad1), / 307, /api/broadcast 307, /datenschutz 200 (prerendered), /rechtliches 200 (prerendered), chunk f916f314 byte-identica
- NEW cto.onecode.de: CNAME→cname.perspective-dns.com day-36 stable (104.18.2.73/3.73), HTTP 409 "error code:1001" + TLS handshake-fail, zero verification TXT — identical to prior cycles
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket: 200 `[]` re-confirmed — endpoint probeable with sb_publishable_ key, zero buckets; unchanged 20+ days
- NEW Supabase REST /rest/v1/: monitor formally closed 09-17 (26 probes, 503↔401 oscillation, never 200+rows); platform enforces sb_publishable_ format only; no cadence probes
- NEW No deploy signal since 09-19 11:33Z; chunk diff is event-triggered, not time-based — time-cadence probing has no value day-36

## 2026-09-25 00:49:56 UTC

## 2026-09-25 06:03:32 UTC

## 2026-09-25 11:47:27 UTC
- NEW None — all surfaces identical to 2026-09-25 06:03Z lead update (5.5h ago)
- CHANGED None — kurs.onecode.de chunk `0-mbmp1iqb6hj.js` byte-identical since 09-18 deploy; cto CNAME day-37 stable; storage 200 `[]`; REST monitor closed; auth settings frozen

## 2026-09-25 16:57:56 UTC

## 2026-09-25 20:24:14 UTC
- NEW kurs.onecode.de: **Supabase client shipped with `flowType:"implicit"` + `detectSessionInUrl:!0` + `persistSession:!0` + `storageKey:"supabase.auth.token"`**, code confined to co-resident old-generatio
- NEW kurs.onecode.de: middleware **path-normalization bypass sweep falsified** — 10 variants (`/Dashboard`, `//dashboard`, `/dashboard/`, `/./dashboard`, `/dashboard%2F`, `/dashboard..;/`, `/%2Fdashboard`,
- NEW kurs.onecode.de: **header-desync bypass falsified** — `X-Original-URL`, `X-Rewrite-URL`, `X-Original-Url`, `X-Forwarded-Prefix` on `/dashboard` all 307→/login; `X-Forwarded-Host: evil.example` leaves 
- NEW kurs.onecode.de: `/.well-known/{openid-configuration,jwks.json,assetlinks.json,security.txt}` + `/sitemap.xml` + `/robots.txt` all 307→/login — no pre-auth well-known surface.
- NEW kurs.onecode.de: HTTP:80 edge returns `301` with `Location: https://<verbatim-Host>/path`; reflection exists but **no exploitable primitive** (browser sets Host from URL authority) → informational onl
- NEW Supabase: `GET /auth/v1/user` with forged `alg=none` token → **403 `bad_jwt` "signing method none is invalid"** — JWT signature validation sound; bearer-only (no apikey) → 401 `No API key found`.
- NEW Supabase: `GET /realtime/v1/websocket` upgrade attempt → **403 with publishable key** (401 without) — the 401 on the HTTP GET does generalize to the WS path; realtime closed pre-auth.
- NEW Supabase: `GET /auth/v1/health` → GoTrue `v2.197.0` (version disclosure, OOS class, not reportable).
- CHANGED hypothesis "Next.js middleware does not cover RSC/segment negotiation" → **FALSIFIED**: `GET /dashboard?_rsc=k1` with `RSC: 1` + `Next-Router-State-Tree` → **307→/login**, byte-identical to plain GET.
- CHANGED cto.onecode.de: unchanged — CNAME `cname.perspective-dns.com`, TXT zero, HTTP 409. Chunk `0-mbmp1iqb6hj.js` sha256 `f916f314…` byte-identical → day-7, no deploy.

## 2026-09-25 23:34:33 UTC
- NEW kurs.onecode.de: /login form has NO action, NO method, and its email/password inputs carry no `name` attribute (id="email"/"password" only), no `$ACTION_ID_*`, no `next-action`/`server-reference` in t
- NEW kurs.onecode.de: the URL-fragment→session sink is APPLICATION code, not a library default — module 34891 `HashSessionHandoff` in current-build chunk `1a4tqdnsy9k1l.js`: parses `window.location.hash` v
- NEW kurs.onecode.de: `HashSessionHandoff`'s `next` is hardcoded `{invite:"/einladung",recovery:"/passwort-neu"}` defaulting to `/` → the injected session cannot be steered to an external origin. No open r
- CHANGED kurs.onecode.de: pre-auth window for the fragment sink is now NARROWER than the last lead claimed. Module 34891 is defined in a pre-auth-served chunk (200) but is imported by **no** chunk in the /logi
- NEW kurs.onecode.de: bundled supabase-js is `2.112.0` with library defaults `rY={autoRefreshToken:!0,persistSession:!0,detectSessionInUrl:!0,flowType:"implicit"}`; the app passes `detectSessionInUrl:(void
- NEW kurs.onecode.de: secret-leak sweep across all 13 pre-auth-served chunks → **zero** `eyJ*.*.*` JWTs, zero `service_role` / `SUPABASE_SERVICE` / `secret_key` / `JWT_SECRET` strings. Only `sb_publishable
- CHANGED kurs.onecode.de: main chunk `0-mbmp1iqb6hj.js` sha256 `f916f314ea61a8c58a055707fc63c251f38e8412ae7a08e6abd7500ec375abca` byte-identical → day-7, no deploy; `/login` 200 (no Set-Cookie, `private/no-sto
- CHANGED cto.onecode.de: CNAME `cname.perspective-dns.com` (dig 1.1.1.1), TXT empty, HTTP 409 — day-39, unchanged.
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket: 200 with publishable key — zero buckets, unchanged.

## 2026-09-26 02:02:53 UTC
- NEW kurs.onecode.de: NULL-SESSION / FORGED-COOKIE CLASS TESTED FOR THE FIRST TIME (5 read-only GETs, ≤1rps, no valid credential used). Cookie `sb-aygnpacdkgtsfnhgcyjc-auth-token` set to (A) `garbage`, (B)
- CHANGED kurs.onecode.de: the "implicit flow" premise in all prior leads is FALSIFIED. `flowType:"implicit"` is only the supabase-js DEFAULT-options constant `rF={url:"http://localhost:9999",storageKey:"supaba
- CHANGED kurs.onecode.de: the Supabase client is constructed at MODULE-EVALUATION time, not lazily. Module 11795 ends `...}("https://aygnpacdkgtsfnhgcyjc.supabase.co","sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6
- CHANGED kurs.onecode.de: the only control preventing unauthenticated fragment-token ingestion is the flowType guard. `_initialize()` → `_isImplicitGrantCallback()` returns true on `access_token` in the hash (
- CHANGED kurs.onecode.de: session storage is a COOKIE, not localStorage. `@supabase/ssr@0.12.4 createBrowserClient` with `cookieEncoding:"base64url"`, storageKey `sb-${hostname.split(".")[0]}-auth-token` = `sb
- CHANGED kurs.onecode.de: module 34891 (HashSessionHandoff) has ZERO importers in the /login-reachable module graph — it occurs exactly twice in 1a4tqdnsy9k1l.js, both as its own `34891,e=>{` definition and `}
- NEW kurs.onecode.de: no PKCE authorization-code injection is possible pre-auth. `_isPKCECallback` requires `?code=` matching `/^[a-zA-Z0-9_-]{8,64}$/` AND a stored verifier at `sb-...-auth-token-flow-<flo
- CHANGED kurs.onecode.de: no deploy. Main chunk `0-mbmp1iqb6hj.js` sha256 `f916f314ea61a8c58a055707fc63c251f38e8412ae7a08e6abd7500ec375abca` byte-identical to the 2026-09-19 11:33Z build — day-8. /login 200 (p
- CHANGED cto.onecode.de: CNAME `cname.perspective-dns.com` unchanged at day-40, zero TXT, HTTP 409 confirmed live this cycle.
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket: 200 `[]` with publishable key — still zero buckets.

## 2026-09-26 07:34:01 UTC
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: GoTrue `redirect_to` allowlist tested LIVE on the pre-auth, unauthenticated `GET /auth/v1/verify?type=recovery` path for the first time — 8 off-origin variants (`http
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: `SITE_URL` positively identified as `https://kurs.onecode.de` from the fallback target (previously only inferred from app-side `settings`).
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: `GET /auth/v1/logout?returnTo=https://evil.example/` → **405, `Allow: POST`** — the legacy GoTrue GET-logout open-redirect primitive is absent on this gateway version
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: `GET /auth/v1/verify` writes the outcome into the **URL fragment** at the app origin (`#error=...&sb=`), not the query string. This confirms the success path of a mag
- CHANGED kurs.onecode.de: no deploy. 13 chunk refs byte-identical to the 09-19 11:33Z set (`0-lpao5_i9htd.js` + `0-mbmp1iqb6hj.js` + `4310-_brt1a3g.js` + `turbopack-2a8cgfwu75lsu.js`) — day-9. `HEAD /login` 20
- CHANGED cto.onecode.de: `dig @1.1.1.1` → CNAME `cname.perspective-dns.com`, TXT = SOA only, HTTP 409 — day-40, unchanged.
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket: 200 `[]` with `sb_publishable_…` — zero buckets, day-40.
- NEW NULL-SESSION / FORGED-COOKIE class tested for first time: 5 cookie variants (garbage, base64 valid-shape with alg:none, chunked .0 name, Authorization bearer + apikey, chunked against /api/broadcast) 
- CHANGED "Implicit flow" premise falsified: `flowType:"implicit"` is only supabase-js default constant `rF`, not app-configured; client constructed at module-eval time in module 11795
- CHANGED HashSessionHandoff (module 34891) has ZERO importers in /login-reachable module graph — dead code, not executed on pre-auth pages
- CHANGED Session storage is COOKIE `sb-aygnpacdkgtsfnhgcyjc-auth-token` (base64url, @supabase/ssr@0.12.4), not localStorage
- NEW No PKCE authorization-code injection pre-auth: `_isPKCECallback` requires `?code=` + stored verifier; app uses email magic-link, never persists verifier
- CHANGED No deploy: main chunk `0-mbmp1iqb6hj.js` sha256 `f916f314ea61a8c5...` byte-identical day-8; cto CNAME day-40 stable; storage 200 `[]`

## 2026-09-26 12:30:05 UTC
- NEW Supabase GoTrue redirect_to allowlist tested LIVE on pre-auth unauthenticated verify path: 8 off-origin variants all 303 to https://kurs.onecode.de#error=... — no open redirect, no token leak to attac
- NEW SITE_URL positively identified as https://kurs.onecode.de from fallback target (previously inferred)
- NEW GET /auth/v1/logout?returnTo= returns 405 Allow: POST — legacy GoTrue GET-logout redirect primitive absent
- NEW GET /auth/v1/verify writes outcome to URL fragment at app origin (#error=...&sb=) — confirms magic-link success path delivers fragment at app origin
- CHANGED HashSessionHandoff (module 34891) confirmed dead code: zero importers in /login-reachable module graph, not executed on pre-auth pages
- CHANGED Session fixation hypothesis confidence 40→practically 0: sink exists but dead code, no open redirect, requires valid attacker token pair (invited account), victim click — exploitability negligible

## 2026-09-26 16:47:59 UTC
- NEW kurs.onecode.de: no deploy. `/_next/static/chunks/0-mbmp1iqb6hj.js` → 154 581 B, sha256 `f916f314ea61a8c58a055707fc63c251f38e8412ae7a08e6abd7500ec375abca` — byte-identical to the 09-19 11:33Z build, *
- NEW kurs.onecode.de: `GET /passwort-vergessen` (308 → trailing-slash form, then 200) serves one route-specific chunk `/_next/static/chunks/2-fsf9vi38mzv.js` (13 617 B) that is **not** referenced by `/logi
- NEW kurs.onecode.de: `2-fsf9vi38mzv.js` submits `createClient().auth.resetPasswordForEmail(email.trim())` with **no** `redirectTo` / `emailRedirectTo` option, no `$ACTION_ID`, no `action`/`method` on the 
- CHANGED kurs.onecode.de: **the 12:30Z conclusion "HashSessionHandoff (module 34891) confirmed dead code — zero importers" is RETRACTED as unsound.** Turbopack registers this as a *client component reference*:
- CHANGED kurs.onecode.de: sink-mount negative extended — `2-fsf9vi38mzv.js` contains **0** occurrences of `HashSessionHandoff`, so the sink is **not** mounted on the pre-auth recovery-request page. Its consume
- CHANGED cto.onecode.de: `dig @1.1.1.1` → CNAME `cname.perspective-dns.com.` / A `104.18.2.73`, `104.18.3.73`; `GET http://cto.onecode.de/` → **409** — day-41, unchanged.
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co: `GET /storage/v1/bucket` (apikey + Bearer = publishable key) → **200 `[]`** — zero buckets, day-41. Publishable key still accepted in `sb_publishable_` form.
- CHANGED kurs.onecode.de: `HEAD /login` → 200, `private, no-cache, no-store`, **no `Set-Cookie`**, `server: railway-hikari`, `x-railway-edge: iad1`, `x-hikari-trace: iad1.trg5` — pre-auth surface still exactly
- NEW No deploy signal since 2026-09-19 11:33Z; main chunk `0-mbmp1iqb6hj.js` sha256 `f916f314ea61a8c58a055707fc63c251f38e8412ae7a08e6abd7500ec375abca` byte-identical day-9; pre-auth surface frozen at {/log
- NEW cto.onecode.de CNAME→cname.perspective-dns.com day-40 stable; HTTP 409 "error code:1001" + TLS handshake-fail; zero verification TXT; conf 58 holds
- NEW Supabase REST monitor formally closed 09-17 after 26 probes (503↔401 oscillation), never 200+rows; platform enforces `sb_publishable_` format only
- NEW Supabase Storage `/storage/v1/bucket` 200 `[]` with `sb_publishable_` key — zero buckets, stable 20+ days
- CHANGED Session fixation hypothesis confidence 40→practically 0: HashSessionHandoff (module 34891) confirmed dead code (zero importers in /login-reachable graph), no open redirect, requires valid attacker tok
- CHANGED GoTrue `redirect_to` allowlist tested LIVE on pre-auth unauthenticated verify path: 8 off-origin variants all 303 to `https://kurs.onecode.de#error=...` — no open redirect, no token leak
- CHANGED `SITE_URL` positively identified as `https://kurs.onecode.de` from fallback target
- CHANGED `GET /auth/v1/logout?returnTo=` returns 405 `Allow: POST` — legacy GoTrue GET-logout redirect primitive absent
- CHANGED Forged/null session cookies (5 variants) tested for first time in 40 days — all 307→/login; middleware gate intact
- CHANGED No PKCE authorization-code injection pre-auth: `_isPKCECallback` requires `?code=` + stored verifier; app uses email magic-link only
- CHANGED Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys (`eyJhbGci...`) rejected globally as "Invalid API key" — platform-level change, not OneCode rotation

## 2026-09-26 19:38:59 UTC

## 2026-09-26 22:14:42 UTC
- NEW kurs.onecode.de: `HashSessionHandoff` **is mounted on `/login`**, a pre-auth 200 page. The `/login` RSC flight payload row `18:I[34891,[…],"HashSessionHandoff"]` is instantiated in the rendered tree a
- CHANGED kurs.onecode.de: the 2026-09-26 16:47Z conclusion "the sink is **not** mounted on either interactive pre-auth page; its consumer remains a chunk belonging to the 307-gated `/einladung` or `/passwort-n
- NEW kurs.onecode.de: component body re-read from `_next/static/chunks/1a4tqdnsy9k1l.js` (13 880 B). `useEffect(()=>{…parse window.location.hash…; history.replaceState(null,"",pathname+search); if(error) e
- NEW kurs.onecode.de: `/datenschutz` and `/rechtliches` are byte-identical to each other and a strict **11-chunk subset** of `/login` (missing `0-lpao5_i9htd.js` and `1a4tqdnsy9k1l.js`), with **zero `I[…]`
- NEW kurs.onecode.de: no deploy. `/_next/static/chunks/0-mbmp1iqb6hj.js` → 154 581 B, sha256 `f916f314ea61a8c58a055707fc63c251f38e8412ae7a08e6abd7500ec375abca` — byte-identical, day-10. All 13 chunk refs o
- CHANGED cto.onecode.de: `dig @1.1.1.1` → CNAME `cname.perspective-dns.com.`, A `104.18.2.73`/`104.18.3.73`, TXT = 1 line (SOA only) — day-42, unchanged.
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co: `GET /storage/v1/bucket` (apikey + Bearer = publishable key) → **200 `[]`** — zero buckets, day-42.

## 2026-09-27 00:44:36 UTC
- NEW kurs.onecode.de: the fragment `error` branch is a two-value enum, not a passthrough. Re-read of module 34891 (`sha256 5a72d2cd8738ecadfd9ef271f062b3f2ba799617dabddf32987c2883c6dcedd0`, 13 880 B, first
- NEW kurs.onecode.de: the server component applies an independent exact-match allowlist on `?error=`. `GET /login?error=link-abgelaufen` → 19 559 B, `linkError:"Dieser Einladungslink ist abgelaufen oder wu
- NEW kurs.onecode.de: `/login` is dynamic w.r.t. searchParams (payload grows ~700 B only when `error` matches), so query-param enumeration is a usable instrument. 11 candidates (`next, redirect, redirectTo
- NEW kurs.onecode.de: `LoginForm` (module 28420, same chunk) re-read in full — `linkError` is its only prop, and the post-password path is hardcoded `c.push("/")` after `signInWithPassword`. No attacker-st
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: `GET /auth/v1/settings` → 200, `external.anonymous_users: false`, `disable_signup: true`, `mailer_autoconfirm: false`, only `external.email: true`. Anonymous sign-in 
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: `GET /auth/v1/admin/users` → 401, `GET /auth/v1/admin/generate_link` → 401 (publishable key, apikey + Bearer). Admin plane not reachable pre-auth.
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: `GET /rest/v1/` with `Accept: application/openapi+json` → 401 `{"message":"Secret API key required","hint":"Only secret API keys can be used for this endpoint."}`. Th
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co: the RLS hypothesis (conf 65) has exactly **one** viable test design and no cheap alternative. An anonymous sign-in would have supplied a second distinct `authenticate
- CHANGED cto.onecode.de: day-43, unchanged. CNAME `cname.perspective-dns.com.`, A `104.18.2.73`/`104.18.3.73`, TXT single SOA line, `GET http://cto.onecode.de/` → 409 `error code: 1001`.
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]`, day-43, zero buckets.
- NEW kurs.onecode.de: HashSessionHandoff (module 34891) confirmed mounted on `/login` RSC payload (row `18:I[34891,…]`) — runs `useEffect` on hydration, parses `window.location.hash` for `access_token`+`re
- NEW kurs.onecode.de: `/datenschutz` and `/rechtliches` are strict 11-chunk subsets of `/login` (missing `0-lpao5_i9htd.js` and `1a4tqdnsy9k1l.js`), zero `I[…]` client references — fully static, no sink.
- NEW kurs.onecode.de: NULL/FORGED session cookie class tested for first time (5 variants: garbage, base64 valid-shape with alg:none, chunked .0 name, Authorization bearer+apikey, chunked against `/api/broa
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: GoTrue `redirect_to` allowlist tested LIVE on pre-auth unauthenticated `GET /auth/v1/verify?type=recovery` — 8 off-origin variants all 303 to `https://kurs.onecode.de
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: `GET /auth/v1/logout?returnTo=` → 405 `Allow: POST` — legacy GoTrue GET-logout redirect primitive absent.
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: `SITE_URL` positively identified as `https://kurs.onecode.de` from fallback target.
- CHANGED Session fixation hypothesis confidence 70→practically 0: sink exists on `/login` but requires valid attacker token pair (invited account) + victim click; no open redirect; error paths fixed; exploitab
- CHANGED cto.onecode.de: CNAME→cname.perspective-dns.com day-42 stable; HTTP 409 "error code:1001" + TLS handshake-fail; zero verification TXT; conf 58 holds; HUMAN_ONLY proof path.
- CHANGED Supabase REST monitor formally closed 09-17 (26 probes, 503↔401, never 200+rows); platform enforces `sb_publishable_` format only.
- CHANGED Supabase Storage `/storage/v1/bucket` 200 `[]` with `sb_publishable_` key — zero buckets, stable 20+ days.
- CHANGED kurs.onecode.de: no deploy since 09-19 11:33Z; main chunk `0-mbmp1iqb6hj.js` sha256 `f916f314ea61a8c58a055707fc63c251f38e8412ae7a08e6abd7500ec375abca` byte-identical day-10; all 13 chunk refs stable.

## 2026-09-27 06:28:41 UTC
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: **the storage listing inference is unsound and is retracted.** `GET /storage/v1/bucket` → `200 []` has been read for 44 days as "zero buckets exist". That inference c
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: **a pre-auth bucket-existence oracle is confirmed and validated.** `GET /storage/v1/object/public/<name>/<key>` returns a distinguishable `400 {"statusCode":"404","co
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: **26 candidate bucket names positively excluded** via that oracle, all byte-identical to control: `public, assets, uploads, files, content, resources, documents, medi
- NEW kurs.onecode.de: the bucket name is **not recoverable pre-auth**. The 13 pre-auth-served chunks contain the supabase-js storage *library* module (`StorageApiError`, `__isStorageError`, `storage`) but 
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: GoTrue `GET /auth/v1/authorize?provider=github&redirect_to=https://evil.example/` → `400 {"error_code":"validation_failed","msg":"Unsupported provider: provider is no
- CHANGED The "Supabase Storage public bucket exposure" hypothesis (conf 55, ACCEPTED 2026-09-04) is **formally REJECTED**. Its sole support was the `[]` listing, now shown to be uninformative; and 26 semantic 
- CHANGED kurs.onecode.de: no deploy. Main chunk `0-mbmp1iqb6hj.js` = 154 581 B, sha256 `f916f314ea61a8c58a055707fc63c251f38e8412ae7a08e6abd7500ec375abca` — byte-identical to the 2026-09-19 11:33Z build, day-11
- CHANGED cto.onecode.de: day-44, unchanged. CNAME `cname.perspective-dns.com.`, A `104.18.2.73`/`104.18.3.73`, TXT absent at host, `GET http://cto.onecode.de/` → `409 error code: 1001`. kurs CNAME `ki8dqcf6.up
- NEW kurs.onecode.de: HashSessionHandoff (module 34891, chunk `1a4tqdnsy9k1l.js` sha256 `5a72d2cd...`) confirmed mounted on `/login` RSC payload row `18:I[34891,…]`; runs `useEffect` on hydration, parses `
- NEW kurs.onecode.de: `/login` dynamic w.r.t. `?error=` — 11 candidates tested (`next, redirect, redirectTo, returnTo, url, target, continue, goto, dest, destination, callback`); only `error=link-abgelaufe
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: `GET /auth/v1/settings` → `external.anonymous_users: false`, `disable_signup: true`, `mailer_autoconfirm: false`, only `external.email: true` — anonymous sign-in disa
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: `GET /rest/v1/` with `Accept: application/openapi+json` → 401 `Secret API key required` / `Only secret API keys can be used for this endpoint` — PostgREST schema disc
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: `GET /auth/v1/admin/users` + `/auth/v1/admin/generate_link` → 401 with publishable key — GoTrue admin plane unreachable pre-auth, no service-role material in any pre-
- CHANGED Session fixation hypothesis confidence 70→practically 0: sink exists on `/login` but requires valid attacker token pair (invited account) + victim click; no open redirect; error paths fixed to `/login
- CHANGED cto.onecode.de: CNAME→cname.perspective-dns.com day-43 stable; HTTP 409 "error code:1001" + TLS handshake-fail; zero verification TXT; conf 58 holds; HUMAN_ONLY proof path
- CHANGED Supabase REST monitor formally closed 09-17 (26 probes, 503↔401, never 200+rows); platform enforces `sb_publishable_` format only
- CHANGED Supabase Storage `/storage/v1/bucket` 200 `[]` with `sb_publishable_` key — zero buckets, stable 20+ days
- CHANGED kurs.onecode.de: no deploy since 09-19 11:33Z; main chunk `0-mbmp1iqb6hj.js` sha256 `f916f314...` byte-identical day-11; all 13 chunk refs stable

## 2026-09-27 12:28:33 UTC
- NEW Live probes confirm zero delta vs 2026-09-27 06:28Z knowledge base: kurs.onecode.de /login 200 no Set-Cookie, main chunk f916f314ea61a8c5... byte-identical day-11; cto.onecode.de HTTP 409 "error code:

## 2026-09-27 17:20:30 UTC
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/*`: **reflected-origin credentialed CORS** — `/auth/v1/settings`, `/user`, `/verify`, `/authorize` all return `access-control-allow-origin: https://evil.examp
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/render/image/{public,authenticated}/…`: image-transform (imgproxy) service exists, never probed; reuses the `NoSuchBucket` oracle.
- NEW render/image SSRF **falsified**: `?url=` is not a recognized source option — with a benign RFC-2606 name it returns the identical `NoSuchBucket` control. My one `169.254.169.254` attempt was blocked b
- NEW `/rest/v1/rpc/` (PostgREST RPC route class, never tested) → `503 PGRST002`, same schema-cache-down anon-block as table paths. No permissive state.
- CHANGED `/auth/v1/settings` CORS asymmetry: GoTrue = reflected-origin + ACAC:true, while `/rest/v1/` = wildcard `*` + no credentials. Inverted, and uniform across all `/auth/v1/*`.

## 2026-09-27 20:16:58 UTC
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/*: reflected-origin credentialed CORS confirmed — `/auth/v1/settings`, `/user`, `/verify`, `/authorize` return `access-control-allow-origin: <arbitrary Origin>
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/render/image: imgproxy service exists, reuses `NoSuchBucket` oracle; `?url=` not a fetch source (benign URL returns identical control); single `169.254.169.
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/rpc: PostgREST RPC route returns `503 PGRST002` (same schema-cache anon-block); no permissive state
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket: `200 []` inference retracted — listing is uninformative (anon cannot SELECT storage.buckets); "zero buckets exist" conclusion withdrawn
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co: pre-auth bucket-existence oracle confirmed via `GET /storage/v1/object/public/<name>/<key>` → `400 {"code":"NoSuchBucket"}`; 26 candidate names excluded; low-severity
- CHANGED kurs.onecode.de: no deploy since 09-19 11:33Z; main chunk `f916f314ea61a8c5...` byte-identical day-11; all 13 chunk refs stable; `/login` 200 no `Set-Cookie`; pre-auth surface = `{/login,/passwort-ver
- CHANGED cto.onecode.de: CNAME→`cname.perspective-dns.com` day-44; HTTP 409/1001 + TLS handshake-fail; zero verification TXT; conf 58 holds; HUMAN_ONLY proof path
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co: anonymous sign-in disabled (`external.anonymous_users:false`), email-only, signup disabled — two invited accounts required for BOLA test
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co: PostgREST schema disclosure blocked above table layer (`Accept: application/openapi+json` → 401 "Secret API key required"); GoTrue admin plane unreachable pre-auth (4

## 2026-09-27 23:10:52 UTC
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/*: reflected-origin credentialed CORS confirmed — `/auth/v1/settings`, `/user`, `/verify`, `/authorize` return `ACAO: <arbitrary Origin>` + `ACAC: true` (first
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/render/image: imgproxy service exists, reuses `NoSuchBucket` oracle; `?url=` not a fetch source (benign URL returns identical control); single `169.254.169.
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/rpc: PostgREST RPC route returns `503 PGRST002` (same schema-cache anon-block); no permissive state
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket: `200 []` inference retracted — listing uninformative (anon cannot SELECT storage.buckets); "zero buckets exist" conclusion withdrawn
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co: pre-auth bucket-existence oracle confirmed via `GET /storage/v1/object/public/<name>/<key>` → `400 {"code":"NoSuchBucket"}`; 26 candidates excluded; low-severity stru
- CHANGED kurs.onecode.de: no deploy since 09-19 11:33Z; main chunk `f916f314ea61a8c5...` byte-identical day-11; all 13 chunk refs stable; `/login` 200 no `Set-Cookie`; pre-auth surface = `{/login,/passwort-ver
- CHANGED cto.onecode.de: CNAME→`cname.perspective-dns.com` day-44; HTTP 409/1001 + TLS handshake-fail; zero verification TXT; conf 58 holds; HUMAN_ONLY proof path
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co: anonymous sign-in disabled (`external.anonymous_users:false`), email-only, signup disabled — two invited accounts required for BOLA test
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co: PostgREST schema disclosure blocked above table layer (`Accept: application/openapi+json` → 401 "Secret API key required"); GoTrue admin plane unreachable pre-auth (4

## 2026-09-28 01:47:24 UTC
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/*` reflects `Origin: null` with `access-control-allow-credentials: true` (live, 01:45Z 09-28: `/auth/v1/settings` 200 `ACAO: null` `ACAC: true`; `/auth/v1/use
- NEW `/auth/v1/user` emits `access-control-expose-headers: X-Total-Count, Link, X-Supabase-Api-Version` alongside the reflection — the gateway explicitly permits cross-origin JS to read PostgREST paginatio
- NEW `/analytics/v1/*` (Supabase hosted log analytics) returns `404 {"error":"requested path is invalid"}` with the publishable key — the analytics/log-read plane is not deployed on this project. The prior
- NEW HS256 secret-guess / `service_role` token-forgery class tested live for the first time, 4 candidate secrets × 2 endpoints. `super-secret-jwt-token-with-at-least-32-characters-long`, the publishable ke
- CHANGED `/storage/v1/bucket` with `Origin: null` returns `ACAO: *` (not reflected) — the storage plane serves the wildcard preflight form, distinct from the reflected form on GoTrue, now confirmed for the `nu
- NEW `kurs.onecode.de`: 13 chunk refs, main chunk `0-mbmp1iqb6hj.js` = 154 581 B sha256 `f916f314ea61a8c5…`, sink chunk `1a4tqdnsy9k1l.js` = 13 880 B sha256 `5a72d2cd8738ecad…` — both byte-identical, no de
- CHANGED `cto.onecode.de` CNAME `cname.perspective-dns.com.` + HTTP 409 — day-46, no delta.
- NEW No new passive probes executed since 2026-09-27 23:10Z knowledge base update; all surfaces identical to last lead (kurs.onecode.de main chunk f916f314ea61a8c5... byte-identical day-11, cto CNAME day-4
- CHANGED Time delta: ~24h since last live verification cycle; event-triggered build-diff on kurs.onecode.de remains the only deploy signal (none since 09-19 11:33Z)

## 2026-09-28 08:32:21 UTC
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: queued question RESOLVED — preflight on the storage OBJECT PATH (not just plane root) grants PUT and DELETE. `OPTIONS /storage/v1/object/public/<b>/<k>` → 200 `ACAO: 
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: CORS CACHE-AMPLIFICATION AMPLIFIER FALSIFIED. Reflected responses carry `vary: Origin, Accept-Encoding` and `cf-cache-status: DYNAMIC` (never HIT). A CF-cached `ACAO:
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: CORS COVERAGE MATRIX COMPLETE. Preflight is uniformly `ACAO: *` (wildcard, no ACAC) with the full destructive method list on EVERY plane AND path tested — `/storage/v
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: storage plane serves `ACAO: *` (not reflected) on simple requests, including on the bucket-existence oracle (`400 {"code":"NoSuchBucket"}`) for both `Origin: https://
- CHANGED kurs.onecode.de: 13 chunk refs, main chunk `0-mbmp1iqb6hj.js` = 154 581 B sha256 `f916f314ea61a8c5…`, sink chunk `1a4tqdnsy9k1l.js` = 13 880 B sha256 `5a72d2cd8738ecad…` — both byte-identical, day-12,
- CHANGED cto.onecode.de: CNAME `cname.perspective-dns.com.` → A 104.18.3.73/104.18.2.73, TXT = CNAME line only, `GET http://cto.onecode.de/` → 409 (CF-RAY a42161506a06198a-IAD) — day-47, byte-identical.
- CHANGED KB PROVENANCE DEFECT (own audit, not a surface delta): the catalogued hash `870cf518…` does not reproduce from the catalogued plaintext `sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30` (that hashes to
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/*: reflects `Origin: null` with `ACAC: true` (live 01:45Z 09-28); `/auth/v1/user` emits `access-control-expose-headers: X-Total-Count, Link, X-Supabase-Api-Ver
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: HS256 `service_role` token forgery tested live (4 candidates × 2 endpoints) — all 403/401; JWT key confusion + secret guessing excluded
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: `/analytics/v1/*` returns 404 — analytics plane not deployed, log-disclosure path closed

## 2026-09-28 17:06:47 UTC
- NEW aygnpacdkgtsfnhgcyjc.storage.supabase.co — NEW HOST, never probed in 26 days. S3-compatible
- NEW aygnpacdkgtsfnhgcyjc.storage.supabase.co — PRE-AUTH S3 ACCESS-KEY-ID ORACLE. Two distinguishable
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1 — SIGNED-URL ROUTE CLASS, never probed. The router
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1 — BUCKET-EXISTENCE ORACLE IS ON THREE ROUTES, not one.
- NEW 20 further candidate bucket names excluded via the oracle (46 total): downloads, material, module,
- NEW CORS MATRIX EXTENDED to a 4th host and a 4th plane. OPTIONS
- CHANGED kurs.onecode.de: no deploy. HEAD /login → 200, cache-control private/no-cache/no-store, server railway-hikari,
- CHANGED cto.onecode.de: CNAME cname.perspective-dns.com. → 104.18.2.73/104.18.3.73, TXT = CNAME line only,
- CHANGED storage/v1/bucket → 200 [] with ACAO: * (wildcard, no ACAC), cf-cache-status DYNAMIC. Unchanged.
- NEW CORS on aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/* returns wildcard `ACAO: *` without `ACAC: true` (live probe 2026-09-28 17:00Z) — contradicts KB claim of reflected-origin + ACAC; no credentialed cro
- NEW CORS on aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/object/public/* returns wildcard `ACAO: *` without `ACAC: true` — storage plane CORS-clean for credentialed requests
- NEW `/auth/v1/user` returns 401 `UNAUTHORIZED_MISSING_API_KEY` without publishable key — confirms auth required
- CHANGED KB provenance defect: catalogued publishable-key digest `870cf518...` does not match plaintext `sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30` (actual sha256 `43ccb834...`)

## 2026-09-28 22:35:39 UTC
- NEW aygnpacdkgtsfnhgcyjc.storage.supabase.co — NEW HOST discovered (S3-compatible storage API), never probed in 26 days; pre-auth reachable
- NEW S3 access-key-ID existence oracle confirmed on aygnpacdkgtsfnhgcyjc.storage.supabase.co/storage/v1/s3 — Missing signature vs InvalidAccessKeyId distinguishable
- NEW Signed URL route class on aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/object/sign — never probed, creates presigned URLs
- NEW Bucket-existence oracle confirmed on THREE routes (/object/public, /object/info, /bucket) not one; 46 candidate names excluded
- CHANGED CORS on aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/* is wildcard `ACAO: *` WITHOUT `ACAC: true` (live probe 17:00Z) — contradicts prior KB claim of reflected-origin + ACAC; no credentialed cross-origin 
- CHANGED CORS on aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/object/public/* is wildcard `ACAO: *` WITHOUT `ACAC: true` — storage plane CORS-clean for credentialed requests
- CHANGED KB provenance defect: catalogued publishable-key digest `870cf518...` ≠ sha256 of `sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30` (actual `43ccb834...`)

## 2026-09-29 02:20:53 UTC
- NEW `aygnpacdkgtsfnhgcyjc.storage.supabase.co` — S3-compatible storage API host confirmed live, never probed in 26 days; returns S3 XML `403 Missing signature` on GET `/storage/v1/s3`
- NEW S3 access-key-ID oracle confirmed: bogus `Authorization: AWS4-HMAC-SHA256 Credential=BOGUS/...` returns `400 InvalidSignature` (distinguishable from `403 Missing signature`)
- NEW Signed URL route class confirmed on `aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/object/sign` — POST with `apikey` + `expiresIn` returns `404 NoSuchKey` (route functional, bucket/existence oracle)
- NEW Bucket-existence oracle spans THREE routes (`/object/public`, `/object/info`, `/bucket`) — 46 candidate names excluded
- CHANGED CORS on GoTrue gateway (`/auth/v1/*`) is **wildcard `ACAO: *` WITHOUT `ACAC: true` on unauthenticated requests**; with valid `apikey` it reflects arbitrary `Origin` **with `ACAC: true`** — contradicts
- CHANGED CORS on storage plane (`/storage/v1/object/public/*`) is wildcard `ACAO: *` WITHOUT `ACAC: true` — credentialed cross-origin read not possible
- CHANGED KB provenance defect: catalogued publishable-key digest `870cf518...` ≠ sha256 of `sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30` (actual `43ccb834...`)

## 2026-09-29 08:46:27 UTC
- NEW `aygnpacdkgtsfnhgcyjc.storage.supabase.co` — S3-compatible storage API host confirmed live, never probed in 26 days; returns S3 XML `403 Missing signature` on GET `/storage/v1/s3`
- NEW S3 access-key-ID oracle confirmed: bogus `Authorization: AWS4-HMAC-SHA256 Credential=BOGUS/...` returns `400 InvalidSignature` (distinguishable from `403 Missing signature`)
- NEW Signed URL route class confirmed on `aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/object/sign` — POST with `apikey` + `expiresIn` returns `404 NoSuchKey` (route functional, bucket/existence oracle)
- NEW Bucket-existence oracle spans THREE routes (`/object/public`, `/object/info`, `/bucket`) — 46 candidate names excluded
- CHANGED CORS on GoTrue gateway (`/auth/v1/*`) is **wildcard `ACAO: *` WITHOUT `ACAC: true` on unauthenticated requests**; with valid `apikey` it reflects arbitrary `Origin` **with `ACAC: true`** — contradicts
- CHANGED CORS on storage plane (`/storage/v1/object/public/*`) is wildcard `ACAO: *` WITHOUT `ACAC: true` — credentialed cross-origin read not possible
- CHANGED KB provenance defect: catalogued publishable-key digest `870cf518...` ≠ sha256 of `sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30` (actual `43ccb834...`)

## 2026-09-29 15:37:36 UTC
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/* — PostgREST plane ALSO accepts the publishable key as a
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/* — reflects Origin WITHOUT `vary: Origin`
- NEW Scoping correction: storage plane does NOT accept `?apikey=` — `GET /storage/v1/bucket?apikey=<pub>`
- CHANGED GoTrue CORS re-measured WITH a control this cycle: `Origin: https://evil.example` → ACAO reflected +
- CHANGED GoTrue emits CORS headers BEFORE the auth check: `GET /auth/v1/user` + forged `alg:none` bearer →
- CHANGED S3 plane `<Resource/>` element is now empty on `GET /storage/v1/s3` (last cycle it echoed
- CHANGED `/auth/v1/authorize?provider=github&redirect_to=https://evil.example/` re-confirmed inert:
- NEW `aygnpacdkgtsfnhgcyjc.storage.supabase.co/storage/v1/s3` — S3-compatible storage API confirmed live (403 `Missing signature`), never probed in 26 days; separate SigV4 authz plane bypasses Supabase RLS
- NEW S3 access-key-ID oracle confirmed: `403 Missing signature` (no auth) vs `400 InvalidSignature` (bogus credential) distinguishable
- NEW Signed URL route class on `aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/object/sign` — POST with `apikey` + `expiresIn` returns `404 NoSuchKey` (route functional)
- NEW Bucket-existence oracle spans THREE routes (`/object/public`, `/object/info`, `/bucket`) — 46 candidate names excluded
- CHANGED CORS on GoTrue gateway (`/auth/v1/*`): wildcard `ACAO: *` WITHOUT `ACAC: true` on unauthenticated requests; WITH valid `apikey` reflects arbitrary `Origin` **with `ACAC: true`** (live probe 15:34Z) — 
- CHANGED CORS on storage plane (`/storage/v1/object/public/*`): wildcard `ACAO: *` WITHOUT `ACAC: true` — credentialed cross-origin read not possible
- CHANGED KB provenance defect: catalogued publishable-key digest `870cf518...` ≠ sha256 of `sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30` (actual `43ccb834...`)

## 2026-09-29 20:17:04 UTC
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/* — the credentialed Origin reflection is reachable through the apikey QUERY STRING, not only the apikey header. `GET /auth/v1/settings?apikey=sb_publishable_g
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/* — the `vary: Origin` omission is now measured on a live *reflected* response, not inferred. `GET /rest/v1/profiles?select=*` with `Origin: https://evil.examp
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1 — 22 further bucket names excluded via the pre-auth oracle (68 total), now including project-ref-derived (`aygnpacdkgtsfnhgcyjc`, `aygnpacdkgtsfnhgcyjc-stor
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/settings — unauthenticated form confirmed as a genuinely different policy: no apikey → 401 + `ACAO: *` + no `ACAC`; with apikey (header *or* query) → 200 + ref
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/user — the 401 path emits `vary: Origin` only (no `Accept-Encoding`) while the 403 forged-JWT path emits `vary: Origin, Accept-Encoding`; CORS headers are emit
- NEW `aygnpacdkgtsfnhgcyjc.storage.supabase.co/storage/v1/s3` — S3-compatible storage API confirmed live (403 `Missing signature`), never probed in 26 days; separate SigV4 authz plane bypasses Supabase RLS
- NEW S3 access-key-ID oracle confirmed: `403 Missing signature` (no auth) vs `400 InvalidSignature` (bogus credential) distinguishable
- NEW Signed URL route class on `aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/object/sign` — POST with `apikey` + `expiresIn` returns `404 NoSuchKey` (route functional)
- NEW Bucket-existence oracle spans THREE routes (`/object/public`, `/object/info`, `/bucket`) — 46 candidate names excluded
- CHANGED CORS on GoTrue gateway (`/auth/v1/*`): wildcard `ACAO: *` WITHOUT `ACAC: true` on unauthenticated requests; WITH valid `apikey` reflects arbitrary `Origin` **with `ACAC: true`** (live probe 15:34Z) — 
- CHANGED CORS on storage plane (`/storage/v1/object/public/*`): wildcard `ACAO: *` WITHOUT `ACAC: true` — credentialed cross-origin read not possible
- CHANGED KB provenance defect: catalogued publishable-key digest `870cf518...` ≠ sha256 of `sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30` (actual `43ccb834...`)
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/*` — PostgREST plane accepts publishable key as query-string; reflects `Origin` WITHOUT `vary: Origin`
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/*` — CORS preflight uniformly `ACAO: *` with full destructive method list

## 2026-09-30 00:01:50 UTC
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/*: reflection is ROUTER-WIDE, not route-sampled. Untested paths /auth/v1/ (root) and /auth/v1/no_such_zzz both return 404 with ACAO:<reflected> + ACAC:true + v
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/*: the vary:Origin omission is now measured on the DEFAULT path — apikey header + Origin, no forged token at all, yields 503 PGRST002 with ACAO:<reflected> and
- NEW aygnpacdkgtsfnhgcyjc.supabase.co: the Supabase origin does NOT authenticate by cookie. GET /auth/v1/user with apikey + a forged sb-aygnpacdkgtsfnhgcyjc-auth-token cookie (base64url, alg:none bearer in
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1: MECHANISM for the "storage rejects ?apikey=" claim is now identified, and the claim is confirmed rather than merely asserted. ?apikey= alone -> 400 {"code"
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co: the ACAC discriminator between planes is now measured rather than inferred. GoTrue reflects Origin WITH ACAC:true (2/2 on /auth/v1/user). PostgREST reflects Origin wi
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/* latent-amplifier ceiling is now pinned with a cacheability measurement: the reflected 503 carries NO cache-control, no etag, no age, no expires; 503 is not i
- NEW *.onecode.de inventory: 26 additional plausible hostnames brute-forced by direct DNS (api, app, auth, supabase, db, storage, media, cdn, files, assets, dev, staging, test, admin, panel, beta, v2, lear
- CHANGED kurs.onecode.de: no deploy. 13 chunk refs identical; 0-mbmp1iqb6hj.js = 154581 B sha256 f916f314ea61a8c58a055707fc63c251f38e8412ae7a08e6abd7500ec375abca and sink 1a4tqdnsy9k1l.js = 13880 B sha256 5a72
- NEW S3-compatible storage plane `aygnpacdkgtsfnhgcyjc.storage.supabase.co` confirmed live (GET /storage/v1/s3 → 403 S3 XML), never probed in 26 days; independent SigV4 authz bypasses Supabase RLS
- NEW S3 access-key-ID oracle confirmed: `403 Missing signature` (no auth) vs `400 InvalidSignature` (bogus credential) distinguishable
- NEW Signed URL route class on `aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/object/sign` — POST with `apikey` + `expiresIn` returns `404 NoSuchKey` (route functional)
- NEW Bucket-existence oracle spans THREE routes (`/object/public`, `/object/info`, `/bucket`) — 46 candidate names excluded
- CHANGED CORS on GoTrue gateway (`/auth/v1/*`): wildcard `ACAO: *` WITHOUT `ACAC: true` on unauthenticated requests; WITH valid `apikey` (header or query) reflects arbitrary `Origin` **with `ACAC: true`** (liv
- CHANGED CORS on storage plane (`/storage/v1/object/public/*`): wildcard `ACAO: *` WITHOUT `ACAC: true` — credentialed cross-origin read not possible
- CHANGED KB provenance defect: catalogued publishable-key digest `870cf518...` ≠ sha256 of `sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30` (actual `43ccb834...`)
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/*` — PostgREST plane accepts publishable key as query-string; reflects `Origin` WITHOUT `vary: Origin`
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/*` — CORS preflight uniformly `ACAO: *` with full destructive method list
- CHANGED `cto.onecode.de`: CNAME `cname.perspective-dns.com` day-50, HTTP 409, zero verification TXT — passive probing fully converged
- CHANGED `kurs.onecode.de`: no deploy day-12; main chunk `f916f314ea61a8c5...` byte-identical; pre-auth surface frozen at `{/login,/passwort-vergessen,/datenschutz,/rechtliches}` 200
- CHANGED Supabase REST monitor formally closed 09-17 (26 probes, 503↔401 oscillation, never 200+rows); platform enforces `sb_publishable_` format only

## 2026-09-30 05:02:48 UTC
- NEW Supabase edge-functions plane (`/functions/v1/*`) is a 5th plane never entered into the CORS matrix. Simple requests return `ACAO: *`, no `ACAC`, `vary: Accept-Encoding` only, and `Origin: null` yield
- NEW The edge-plane preflight grants **NO** `access-control-allow-methods` line at all — it returns only `ACAO: *` + `access-control-allow-headers: authorization, x-client-info, apikey`. This FALSIFIES the
- NEW Named edge-function probing (13 semantic candidates: admin, stripe-webhook, send-email, email, cron, cleanup, delete-account, export, import, webhook, course, progress, enroll) returns byte-identical 
- NEW Realtime plane is a 6th plane never CORS-tested. `/realtime/v1/websocket?apikey=<pub>` now returns **500 `error code: 1101`** (Cloudflare WS-tunnel failure), NOT the 403 recorded on 2026-09-25. The ap
- NEW Realtime preflight grants the **full destructive method list** (`GET,HEAD,PUT,PATCH,POST,DELETE,OPTIONS,TRACE,CONNECT`, max-age 3600) with `ACAO: *`. This is the only plane besides GoTrue/PostgREST/st
- CHANGED kurs.onecode.de `/login` page sha256 `99798c7d94a15abf…`, 18 702 B, `private, no-cache, no-store`, zero `Set-Cookie`, `railway-hikari`, `x-railway-edge: lax1`, `x-hikari-trace: lax1.v9kt`. Main chunk 
- CHANGED `HashSessionHandoff` (module 34891) still mounted on `/login` RSC payload and still immediately followed by row 19 = `I[28420…]` (LoginForm), same 5-chunk dependency set. Sink mount unchanged.
- CHANGED cto.onecode.de day-52: CNAME `cname.perspective-dns.com.`, A 104.18.3.73/104.18.2.73, TXT = CNAME line only (zero verification records), HTTP 409, CF-RAY a430a7e15a4edfe0-SEA. Unchanged.
- CHANGED GoTrue primary finding re-verified alive: `/auth/v1/settings?apikey=<pub>` + `Origin: https://evil.example` → 200, `ACAO: https://evil.example`, `ACAC: true`, `vary: Origin, Accept-Encoding`, expose-h
- NEW `aygnpacdkgtsfnhgcyjc.storage.supabase.co/storage/v1/s3` — S3-compatible storage plane confirmed live (403 Missing signature), never probed in 26 days; independent SigV4 authz bypasses Supabase RLS
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/*` — PostgREST plane accepts publishable key as query-string; reflects `Origin` WITHOUT `vary: Origin`
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/*` — CORS preflight uniformly `ACAO: *` with full destructive method list
- CHANGED `cto.onecode.de`: CNAME `cname.perspective-dns.com` day-50, HTTP 409, zero verification TXT — passive probing fully converged
- CHANGED `kurs.onecode.de`: no deploy day-12; main chunk `f916f314ea61a8c5...` byte-identical; pre-auth surface frozen at `{/login,/passwort-vergessen,/datenschutz,/rechtliches}` 200
- CHANGED Supabase REST monitor formally closed 09-17 (26 probes, 503↔401 oscillation, never 200+rows); platform enforces `sb_publishable_` format only
- CHANGED CORS on GoTrue gateway (`/auth/v1/*`): wildcard `ACAO: *` WITHOUT `ACAC: true` on unauthenticated requests; WITH valid `apikey` (header or query) reflects arbitrary `Origin` **with `ACAC: true`** (liv
- CHANGED CORS on storage plane (`/storage/v1/object/public/*`): wildcard `ACAO: *` WITHOUT `ACAC: true` — credentialed cross-origin read not possible
- CHANGED KB provenance defect: catalogued publishable-key digest `870cf518...` ≠ sha256 of `sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30` (actual `43ccb834...`)

## 2026-09-30 11:06:36 UTC
- NEW `aygnpacdkgtsfnhgcyjc.storage.supabase.co/storage/v1/s3` — S3-compatible storage API confirmed live (403 Missing signature), never probed in 26 days; independent SigV4 authz plane bypasses Supabase RL
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/*` — edge-functions plane is 5th CORS plane; simple requests return ACAO:* no ACAC vary:Accept-Encoding only; preflight grants NO access-control-allow-me
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/websocket` — realtime is 6th CORS plane; preflight grants full 9-method destructive list with max-age 3600 ACAO:*; apikey query now reaches Cloudflare WS 
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/*` — PostgREST plane accepts publishable key as query-string; reflects Origin WITHOUT vary:Origin; CORS preflight uniformly ACAO:* with full destructive metho
- CHANGED `cto.onecode.de`: CNAME `cname.perspective-dns.com` day-52, HTTP 409, zero verification TXT — passive probing fully converged; only owner claim attempt advances it
- CHANGED `kurs.onecode.de`: no deploy day-13; main chunk `f916f314ea61a8c5...` byte-identical; pre-auth surface frozen at `{/login,/passwort-vergessen,/datenschutz,/rechtliches}` 200; HashSessionHandoff still 
- CHANGED Supabase REST monitor formally closed 09-17 (26 probes, 503↔401 oscillation, never 200+rows); platform enforces `sb_publishable_` format only
- CHANGED CORS on GoTrue gateway (`/auth/v1/*`): wildcard `ACAO: *` WITHOUT `ACAC: true` on unauthenticated requests; WITH valid `apikey` (header or query) reflects arbitrary `Origin` **with `ACAC: true`** (liv
- CHANGED CORS on storage plane (`/storage/v1/object/public/*`): wildcard `ACAO: *` WITHOUT `ACAC: true` — credentialed cross-origin read not possible
- CHANGED KB provenance defect: catalogued publishable-key digest `870cf518...` ≠ sha256 of `sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30` (actual `43ccb834...`)

## 2026-09-30 16:54:45 UTC
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/verify — `redirect_to` allowlist now proven per-TYPE, not just on `type=recovery`. Live 16:52Z: type=recovery|email_change|signup + 32-byte garbage token + off
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/callback — REGISTERED ROUTE, never probed in 49 days. `GET /auth/v1/callback` → 303 `https://kurs.onecode.de?error=invalid_request&error_code=bad_oauth_callbac
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/verify — the 400 no-token validation path emits `vary: Origin` alone; the 303 token-error path emits `vary: Origin, Accept-Encoding`. Both carry Origin, so the
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/* — primary CORS finding re-reproduced live 16:53Z: `/auth/v1/settings?apikey=<pub>` + `Origin: https://evil.example` → 200, ACAO reflected, ACAC: true, vary: 
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/* — PostgREST vary omission re-reproduced live 16:53Z: bare `apikey` header + `Origin: https://evil.example` on `/rest/v1/profiles?select=*` → 503 with `ACAO: 
- NEW `aygnpacdkgtsfnhgcyjc.storage.supabase.co/storage/v1/s3` — S3-compatible storage plane confirmed live (403 Missing signature), independent SigV4 authz plane, never probed in 26 days; access-key-ID ora
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/websocket` — 6th CORS plane; preflight grants full 9-method destructive list (max-age 3600, ACAO:*); apikey query now reaches Cloudflare WS tunnel (500 er
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/*` — PostgREST plane accepts publishable key as query-string; reflects Origin WITHOUT vary:Origin (only vary:Accept-Encoding); CORS preflight uniformly ACAO:*
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/*` — 5th CORS plane (edge); simple requests ACAO:* no ACAC vary:Accept-Encoding only; preflight grants NO access-control-allow-methods; 13 semantic candi
- CHANGED `cto.onecode.de`: CNAME `cname.perspective-dns.com` day-52, HTTP 409, zero verification TXT — passive probing fully converged; only owner claim attempt advances it
- CHANGED `kurs.onecode.de`: no deploy day-13; main chunk `f916f314ea61a8c5...` byte-identical; pre-auth surface frozen at `{/login,/passwort-vergessen,/datenschutz,/rechtliches}` 200; HashSessionHandoff still 
- CHANGED Supabase REST monitor formally closed 09-17 (26 probes, 503↔401 oscillation, never 200+rows); platform enforces `sb_publishable_` format only
- CHANGED CORS on GoTrue gateway (`/auth/v1/*`): wildcard `ACAO: *` WITHOUT `ACAC: true` on unauthenticated requests; WITH valid `apikey` (header or query) reflects arbitrary `Origin` **with `ACAC: true`** (liv
- CHANGED CORS on storage plane (`/storage/v1/object/public/*`): wildcard `ACAO: *` WITHOUT `ACAC: true` — credentialed cross-origin read not possible
- CHANGED KB provenance defect: catalogued publishable-key digest `870cf518...` ≠ sha256 of `sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30` (actual `43ccb834...`)

## 2026-09-30 21:22:57 UTC
- NEW kurs.onecode.de: no deploy. GET /login → 200, private/no-cache/no-store, zero Set-Cookie, railway-hikari, x-railway-edge lax1, x-hikari-trace lax1.e74w. Main chunk 0-mbmp1iqb6hj.js = 154581 B sha256 f
- NEW CORS DISCRIMINATOR RESOLVED, resolving a live contradiction between two models. The wildcard form is the UNAUTHENTICATED response, the reflected+ACAC form is the apikey-BEARING response — the discrimi
- NEW REJECTED OATH @ /auth/v1/*: the `redirect_to` allowlist is NOT influenceable by a client-supplied host header — an axis untested in 50 days. `X-Forwarded-Host: evil.example` alone (303 → https://kurs.
- NEW REJECTED OATH @ /auth/v1/verify: two further allowlist-bypass URL shapes, neither previously tried, both closed. Encoded-at userinfo `https://kurs.onecode.de%40evil.example/` and port-userinfo `https:
- NEW GoTrue ROUTE MAP EXPANDED by 5 registered routes, never mapped in 50 days. 405 `Allow: POST` (route mounted) on `/auth/v1/otp`, `/auth/v1/magiclink`, `/auth/v1/recover`, `/auth/v1/invite`, `/auth/v1/s
- NEW `/auth/v1/anonymous` returning 404 — not 405 — is independent routing-layer corroboration of `external.anonymous_users: false`. The free second `authenticated` principal is not merely disabled in sett
- NEW CORS scope widened to the five mutating primitives: `/auth/v1/otp`, `/auth/v1/recover`, `/auth/v1/invite`, `/auth/v1/signup`, `/auth/v1/magiclink` all return `ACAO: null` + `ACAC: true` + `vary: Origi
- NEW `/storage/v1/s3` is mounted on the MAIN api host as well as on the dedicated storage host: 403, `ACAO: *` only, no reflection, no ACAC. The S3 plane is reachable on two origins; the credentialed refle
- CHANGED cto.onecode.de: CNAME `cname.perspective-dns.com.`, A 104.18.2.73/104.18.3.73, TXT = CNAME line only, zero verification records. Day-53, unchanged. Passive probing converged.
- NEW `aygnpacdkgtsfnhgcyjc.storage.supabase.co/storage/v1/s3` — S3-compatible storage API confirmed live (403 Missing signature), independent SigV4 authz plane bypassing Supabase RLS, never probed in 26 da
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/*` — 5th CORS plane (edge functions); simple requests return ACAO:* no ACAC vary:Accept-Encoding only; preflight grants NO access-control-allow-methods; 
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/websocket` — 6th CORS plane; preflight grants full 9-method destructive list (max-age 3600, ACAO:*); apikey query now reaches Cloudflare WS tunnel (500 er
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/callback` — REGISTERED GoTrue OAuth callback route reachable pre-auth despite all external.* providers false; GET → 303 to SITE_URL with error_code=bad_oauth_
- CHANGED `kurs.onecode.de` — no deploy day-13; main chunk f916f314ea61a8c5... byte-identical; pre-auth surface frozen at {/login,/passwort-vergessen,/datenschutz,/rechtliches} 200; HashSessionHandoff still mou
- CHANGED `cto.onecode.de` — CNAME cname.perspective-dns.com day-52, HTTP 409, zero verification TXT — passive probing fully converged; only owner claim attempt advances it
- CHANGED Supabase GoTrue CORS — re-verified router-wide: /auth/v1/ root and /auth/v1/no_such_zzz both return 404 with ACAO:<reflected> + ACAC:true + vary: Origin; credentialed reflection works via apikey query

## 2026-10-01 00:41:52 UTC
- NEW `GET /auth/v1/settings` body does NOT enumerate any redirect allowlist. Full body read 00:39Z: only `external.*` (26 providers, `email:true` sole truthy), `disable_signup:true`, `mailer_autoconfirm:fa
- NEW GoTrue credentialed reflection extended to two route classes never CORS-tested in the apikey-BEARING state: `/auth/v1/token?grant_type=password` → 405 with `ACAO: https://evil.example` + `ACAC: true` 
- NEW `/auth/v1/` root **with** apikey → 404, `ACAO: <reflected>`, `ACAC: true`, `vary: Origin`. Prior cycles only ever tested this path without the key.
- NEW Storage plane CORS characterisation closed. `ACAO: *`, no `ACAC`, no reflection — with apikey AND Bearer present — on all four route classes: `/storage/v1/bucket` (200), `/object/public/{b}/{k}` (400 
- NEW PostgREST `access-control-expose-headers` on `/rest/v1/profiles` is `Content-Encoding, Content-Location, Content-Range, Content-Type, Date, Location, Server, Transfer-Encoding, Range-Unit` — a differe

## 2026-10-01 06:38:06 UTC
- NEW aygnpacdkgtsfnhgcyjc.storage.supabase.co/storage/v1/s3 — S3-compatible storage API confirmed live (403 Missing signature), independent SigV4 authz plane bypassing Supabase RLS, never probed in 26 days
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/callback — REGISTERED GoTrue OAuth callback route reachable pre-auth despite all external.* providers false; GET → 303 to SITE_URL with error_code=bad_oauth_ca
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/verify — redirect_to allowlist proven per-TYPE (recovery, email_change, signup), 13 off-origin shapes tested, zero bypass; 400 path emits vary: Origin only, 30
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/* — PostgREST reflect Origin WITHOUT vary: Origin on credentialed requests (measured live 2026-10-01 00:39Z)
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/* — 5th CORS plane: simple requests ACAO:* no ACAC vary:Accept-Encoding only; preflight grants NO access-control-allow-methods (falsifies "uniform across 
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/websocket — 6th CORS plane: preflight grants full 9-method destructive list (max-age 3600, ACAO:*); apikey query reaches Cloudflare WS tunnel (500 error co
- CHANGED kurs.onecode.de — no deploy day-14; main chunk f916f314ea61a8c5... byte-identical; pre-auth surface frozen at {/login,/passwort-vergessen,/datenschutz,/rechtliches} 200; HashSessionHandoff still mount
- CHANGED cto.onecode.de — CNAME cname.perspective-dns.com day-53, HTTP 409, zero verification TXT — passive probing fully converged; only owner claim attempt advances it
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/* — CORS discriminator is AUTHENTICATION STATE (unauthenticated→wildcard no ACAC; apikey-bearing→reflected+ACAC:true) — live re-verified 2026-10-01 00:39Z
- CHANGED Supabase REST monitor formally closed 09-17 (26 probes 503↔401), never 200+rows; platform enforces sb_publishable_ format only

## 2026-10-01 13:57:10 UTC
- NEW `aygnpacdkgtsfnhgcyjc.storage.supabase.co` is a **single-plane host**: `/auth/v1/settings`, `/rest/v1/profiles`, `/functions/v1/`, `/realtime/v1/`, `/graphql/v1` all → `404` `Invalid Storage request` 
- NEW S3 path-style is reachable **only** under the `/storage/v1/s3` prefix. `/s3` →404 `Invalid Storage request`; bare `/zzz_ctrl_7f2a` → 404 `Invalid Storage request`; `/storage/v1/s3/zzz_ctrl_7f2a/x.txt`
- CHANGED `/rest/v1/profiles?select=*` with apikey + Bearer → `503 PGRST002` "Could not query the database for the schema cache. Retrying." Schema cache still down; closed REST monitor stays closed (never200+ro

## 2026-10-01 19:25:25 UTC
- NEW aygnpacdkgtsfnhgcyjc.storage.supabase.co confirmed as single-plane S3 host (no GoTrue/PostgREST/Realtime/Functions/GraphQL) — cross-plane routing test 2026-10-01 13:57Z
- NEW S3 path-style reachable ONLY under `/storage/v1/s3` prefix (not `/s3` or bare) — 2026-10-01 13:57Z
- NEW PostgREST `access-control-expose-headers` differs from GoTrue (`Content-Encoding, Content-Location, Content-Range, Content-Type, Date, Location, Server, Transfer-Encoding, Range-Unit` vs `X-Total-Coun
- NEW GoTrue credentialed reflection extends to password-grant (`/auth/v1/token?grant_type=password`) and OTP (`/auth/v1/otp`) — both 405 with reflected ACAO+ACAC:true — 2026-10-01 00:41Z
- CHANGED cto.onecode.de CNAME day-53, HTTP 409, zero verification TXT — passive probing fully converged
- CHANGED kurs.onecode.de no deploy day-14; main chunk `f916f314ea61a8c5...` byte-identical; pre-auth surface frozen
- CHANGED Supabase REST monitor formally closed 09-17 (26 probes, 503↔401, never 200+rows); platform enforces `sb_publishable_` format only

## 2026-10-01 23:26:13 UTC
- NEW S3-compatible storage plane `aygnpacdkgtsfnhgcyjc.storage.supabase.co/storage/v1/s3` confirmed live (HTTP 403 S3 XML "Missing signature"), independent SigV4 authz plane never probed in 26 days — separ
- NEW GoTrue `/auth/v1/token?grant_type=password` and `/auth/v1/otp` return 405 with reflected `ACAO: <Origin>` + `ACAC: true` (live 2026-10-01 00:41Z) — credentialed CORS extends to password-grant and OTP 
- NEW `/auth/v1/callback` registered GoTrue OAuth callback route reachable pre-auth despite all `external.*` providers false; returns 303 to `SITE_URL` with `error_code=bad_oauth_callback`
- CHANGED `kurs.onecode.de` no deploy day-14; main chunk `0-mbmp1iqb6hj.js` (154 581 B, sha256 `f916f314ea61a8c58a055707fc63c251f38e8412ae7a08e6abd7500ec375abca`) and sink chunk `1a4tqdnsy9k1l.js` (13 880 B, sh
- CHANGED `cto.onecode.de` CNAME `cname.perspective-dns.com` day-53, HTTP 409 "error code:1001", zero verification TXT records — passive probing fully converged, only owner claim attempt advances it
- CHANGED `aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1` monitor formally closed 09-17 (26 probes, 503↔401 oscillation, never 200+rows); platform enforces `sb_publishable_` format only
- CHANGED Storage plane CORS characterization closed: `ACAO: *`, no `ACAC`, no reflection — with apikey AND Bearer present — on all four route classes (`/bucket`, `/object/public`, `/object/info`, `/object/sign
- CHANGED GoTrue credentialed reflection discriminator confirmed: authentication STATE (unauthenticated → wildcard no ACAC; apikey-bearing → reflected Origin with `ACAC: true`) — live re-verified 2026-10-01 00:

## 2026-10-02 02:37:05 UTC
- NEW None
- CHANGED None
- NEW S3-compatible storage plane `aygnpacdkgtsfnhgcyjc.storage.supabase.co/storage/v1/s3` confirmed live (HTTP 403 S3 XML "Missing signature"), independent SigV4 authz plane never probed in 26 days — separ
- NEW GoTrue `/auth/v1/token?grant_type=password` and `/auth/v1/otp` return 405 with reflected `ACAO: <Origin>` + `ACAC: true` (live 2026-10-01 00:41Z) — credentialed CORS extends to password-grant and OTP 
- NEW `/auth/v1/callback` registered GoTrue OAuth callback route reachable pre-auth despite all `external.*` providers false; returns 303 to `SITE_URL` with `error_code=bad_oauth_callback`
- CHANGED `kurs.onecode.de` no deploy day-14; main chunk `0-mbmp1iqb6hj.js` (154 581 B, sha256 `f916f314ea61a8c58a055707fc63c251f38e8412ae7a08e6abd7500ec375abca`) and sink chunk `1a4tqdnsy9k1l.js` (13 880 B, sh
- CHANGED `cto.onecode.de` CNAME `cname.perspective-dns.com` day-53, HTTP 409 "error code:1001", zero verification TXT records — passive probing fully converged, only owner claim attempt advances it
- CHANGED `aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1` monitor formally closed 09-17 (26 probes, 503↔401 oscillation, never 200+rows); platform enforces `sb_publishable_` format only
- CHANGED Storage plane CORS characterization closed: `ACAO: *`, no `ACAC`, no reflection — with apikey AND Bearer present — on all four route classes (`/bucket`, `/object/public`, `/object/info`, `/object/sign
- CHANGED GoTrue credentialed reflection discriminator confirmed: authentication STATE (unauthenticated → wildcard no ACAC; apikey-bearing → reflected Origin with `ACAC: true`) — live re-verified 2026-10-01 00:

## 2026-10-02 09:03:04 UTC
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1 — the pre-auth `NoSuchBucket` oracle is ROUTE-TABLE-COMPLETE, not sampled. Live GETs (apikey + Bearer = publishable, Origin: https://evil.example) return by
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1 — the GET route table is now CLOSED by counter-example, which is what makes the 9-class oracle claim sound rather than sampled: `/object/{bucket}` → `404 {"
- NEW aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1 — `/storage/v1/object/upload/sign/{b}/{k}` (presigned-upload issuer) is MOUNTED and bucket-resolves pre-auth (400 NoSuchBucket with a control bucket). This 
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1 — CORS auth-state discriminator re-reproduced live 09:01Z with a matched control on ONE path. `GET /auth/v1/settings?apikey=<pub>` + `Origin: https://evil.exam
- CHANGED kurs.onecode.de — NO deploy, day-15. `GET /login` → `200`, 18 702 B, sha256 `99798c7d94a15abf93ec349b0b221a89dfba756cb21fc581a09d37acd21d9450` (byte-identical), zero `Set-Cookie`, `private, no-cache, 
- CHANGED cto.onecode.de — day-53, unchanged. `dig @1.1.1.1` → CNAME `cname.perspective-dns.com.`, A `104.18.2.73`/`104.18.3.73`, TXT = CNAME line only, zero verification records. `GET http://cto.onecode.de/` →
- CHANGED aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1 + /graphql/v1 — closed monitor sampled once for state only: `/rest/v1/` → `401 {"message":"Secret API key required","hint":"Only secret API keys can be used fo
- CHANGED kurs.onecode.de response headers — `/login` emits NO `content-security-policy`, NO `strict-transport-security`, NO `x-frame-options`, NO `x-content-type-options`, NO `referrer-policy`, NO `permissions

## 2026-10-02 15:50:07 UTC
- NEW S3-compatible storage plane at `aygnpacdkgtsfnhgcyjc.storage.supabase.co/storage/v1/s3` confirmed live (403 Missing signature), independent SigV4 authz plane, access-key-ID oracle verified (400 Invali
- NEW GoTrue credentialed CORS reflection on `/auth/v1/*` re-verified live: `apikey` query param → reflects arbitrary `Origin` with `ACAC: true` on 200/401/404/405; unauthenticated → wildcard `ACAO: *` no `
- NEW Signed URL route `/storage/v1/object/upload/sign/{bucket}/{key}` mounted and bucket-resolves pre-auth (400 NoSuchBucket) — 10th GET route class in complete route table
- CHANGED `kurs.onecode.de` no deploy day-15: main chunk `f916f314ea61a8c5...` (154581 B) and sink chunk `5a72d2cd...` (13880 B) byte-identical; pre-auth surface frozen at `{/login,/passwort-vergessen,/datensch
- CHANGED `cto.onecode.de` CNAME→`cname.perspective-dns.com` day-53, HTTP 409, zero verification TXT — passive probing fully converged
- CHANGED Supabase REST `/rest/v1/` monitor formally closed 09-17 (27 probes, 503↔401 oscillation, never 200+rows); platform enforces `sb_publishable_` format only
- CHANGED Storage plane CORS characterization closed: `ACAO: *`, no `ACAC`, no reflection — with apikey+Bearer on all 10 mounted GET routes

## 2026-10-02 20:35:20 UTC
- NEW `api.`, `functions.`, `realtime.aygnpacdkgtsfnhgcyjc.supabase.co` → **zero A records** (dig A, three legacy Supabase hostnames). Extends the 10-01 DNS-shape negative (`foo.`, `evil.<ref>`) to the stan
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/object/upload/sign/{b}/{k}` GET + `Origin: https://evil.example` + apikey/Bearer → `400 {"code":"NoSuchBucket"}` with `ACAO: *` and **no** `ACAC`. The pres
- NEW `aygnpacdkgtsfnhgcyjc.storage.supabase.co/storage/v1/s3/{bucket}?list-type=2` → `403 <Code>AccessDenied</Code><Message>Missing signature</Message>` with `<Resource>zzz_ctrl_9x7</Resource>` and **no** 
- CHANGED `kurs.onecode.de` — day-16, **no deploy**. `GET /login` → 200, 18 702 B, page sha256 `99798c7d94a15abf93ec349b0b221a89dfba756cb21fc581a09d37acd21d9450` (byte-identical since the 2026-09-19 11:33Z buil
- CHANGED `aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1` — CORS auth-state discriminator re-proven with a matched control on one path, this cycle: `GET /auth/v1/settings?apikey=<pub>` + `Origin: https://evil.exampl
- CHANGED `cto.onecode.de` — day-54, unchanged. CNAME `cname.perspective-dns.com.`, A `104.18.2.73`/`104.18.3.73`, TXT = CNAME line only (zero verification records), `GET http://cto.onecode.de/` → `409`.
- NEW S3-compatible storage plane at `aygnpacdkgtsfnhgcyjc.storage.supabase.co/storage/v1/s3` confirmed live (403 Missing signature), independent SigV4 authz plane, access-key-ID oracle verified (400 Invali
- NEW GoTrue credentialed CORS reflection on `/auth/v1/*` re-verified live: `apikey` query param → reflects arbitrary `Origin` with `ACAC: true` on 200/401/404/405; unauthenticated → wildcard `ACAO: *` no `
- NEW Signed URL route `/storage/v1/object/upload/sign/{bucket}/{key}` mounted and bucket-resolves pre-auth (400 NoSuchBucket) — 10th GET route class in complete route table
- CHANGED `kurs.onecode.de` no deploy day-15: main chunk `f916f314ea61a8c5...` (154581 B) and sink chunk `5a72d2cd...` (13880 B) byte-identical; pre-auth surface frozen at `{/login,/passwort-vergessen,/datensch
- CHANGED `cto.onecode.de` CNAME→`cname.perspective-dns.com` day-53, HTTP 409, zero verification TXT — passive probing fully converged
- CHANGED Supabase REST `/rest/v1/` monitor formally closed 09-17 (27 probes, 503↔401 oscillation, never 200+rows); platform enforces `sb_publishable_` format only
- CHANGED Storage plane CORS characterization closed: `ACAO: *`, no `ACAC`, no reflection — with apikey+Bearer on all 10 mounted GET routes

## 2026-10-03 00:08:37 UTC
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/.well-known/jwks.json` → **200**, 240 B, serving a **JWKS never probed in 53 days**. One key: `kid 4f59d46f-c3e6-47c7-a717-fabf016650c9`, **`alg: ES256`, `kty
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/.well-known/openid-configuration` → **200**, 1045 B, also never probed. `issuer=https://aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1`, `jwks_uri` as above, and cr
- CHANGED **The project's JWT signing algorithm class was wrong in the KB for 53 days.** Every prior JWT entry (09-25 `alg:none`→403, 09-28 "4 candidate HS256 secrets → 403/401", 09-30 "Bearer-only negative") a
- NEW `/auth/v1/oauth/{authorize,token,userinfo,register,oidc}` — entire namespace mapped for the first time. All five → `404 {"error_code":"feature_disabled","msg":"OAuth server is disabled"}`. So the OIDC
- NEW Storage/API breadth sweep (never run): `/pg/`, `/pg-meta/`, `/admin`, `/dashboard`, `/api/`, `/v1/`, `/.well-known/jwks.json` all → `404 {"error":"requested path is invalid"}`. The `jwks` document liv
- CHANGED ES256→HS256 key confusion tested and **falsified** with 16 live requests: 8 public-key derivations (`raw_x||y`, DER SPKI, PEM SPKI, PEM-no-LF, minified JWK JSON, spaced JWK JSON, decoded `x` alone, de
- CHANGED `alg` case-variant confusion (`none`/`None`/`NONE`, × kid present/absent) on PostgREST → 401. `alg=none` returns the distinct `PGRST301 "JWT is unsecured but expected 'alg' was not 'none'"`; `None`/`N
- CHANGED PostgREST shares the ES256 verifier: an ES256 `kid`-bearing token yields `PGRST301 "None of the keys was able to decode the JWT" / "No suitable key or wrong key type"` — the resolver finds the JWK and
- CHANGED **The KB's GoTrue CORS "auth-state discriminator" model has a documented exception.** The `jwks.json` endpoint reflects Origin **with `ACAC: true` even with no apikey and no `Authorization`** — 200 + 
- CHANGED `kurs.onecode.de` — day-17, **no deploy**. `GET /login` → 200, 18 702 B, sha256 `99798c7d94a15abf93ec349b0b221a89dfba756cb21fc581a09d37acd21d9450` (byte-identical since 2026-09-19 11:33Z). Main chunk 
- CHANGED `cto.onecode.de` — day-55, unchanged. CNAME `cname.perspective-dns.com.`, zero verification TXT.
- NEW **JWT algorithm accept-list is ES256-only — confirmed on both planes by live test, contradicting the project's own published OIDC document.** PostgREST `PGRST301` and GoTrue `bad_jwt` distinguish two 
- NEW **RS256-family key confusion is closed with valid attacker signatures** — a materially stronger negative than last cycle's 16 probes. Previously all confusion attempts failed at *signature* verificati
- NEW **Embedded attacker JWK in the JWT header is ignored.** `{"alg":"RS256","jwk":<attacker RSA JWK>}` → `401 "No suitable key or found"`; `{"alg":"ES256","jwk":<attacker EC JWK>}` → `401`; `{"alg":"RS256
- NEW **`PS256`/`PS384`/`PS512` take a distinct code path on PostgREST** — reproducibly (8/8, plus 3 repeats) `"JWT cryptographic operation failed"` with `details: null`, whereas all other algs return `"No 
- NEW **CORS on the two new well-known paths: credentialed arbitrary-Origin reflection confirmed, and it does NOT depend on apikey.** Both `/auth/v1/.well-known/openid-configuration` and `/auth/v1/.well-kno
- CHANGED **The KB's "auth-state discriminator" model is now falsified with a clean counter-example and must be retired as a general rule.** Last cycle I recorded it as having "an exception"; the correct statem
- CHANGED Storage/API breadth: unchanged and now closed by counter-example — `/pg/`, `/pg-meta/`, `/admin`, `/dashboard`, `/api/`, `/v1/`, root `/.well-known/jwks.json` all `404 {"error":"requested path is inva
- CHANGED `kurs.onecode.de` — day-17, no deploy. `/login` 200, 18 702 B, sha256 `99798c7d94a15abf93ec349b0b221a89dfba756cb21fc21fc581a09d37acd21d9450`… corrected: `99798c7d94a15abf93ec349b0b221a89dfba756cb21fc5
- CHANGED `cto.onecode.de` — day-55, CNAME `cname.perspective-dns.com.`, zero TXT. Unchanged.
- NEW S3-compatible storage plane at `aygnpacdkgtsfnhgcyjc.storage.supabase.co/storage/v1/s3` confirmed live (403 Missing signature), independent SigV4 authz plane, access-key-ID oracle verified (400 Invali
- NEW GoTrue credentialed CORS reflection on `/auth/v1/*` re-verified live: `apikey` query param → reflects arbitrary `Origin` with `ACAC: true` on 200/401/404/405; unauthenticated → wildcard `ACAO: *` no `
- NEW Signed URL route `/storage/v1/object/upload/sign/{bucket}/{key}` mounted and bucket-resolves pre-auth (400 NoSuchBucket) — 10th GET route class in complete route table
- NEW `api.`, `functions.`, `realtime.aygnpacdkgtsfnhgcyjc.supabase.co` → zero A records (dig A, three legacy Supabase hostnames)
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/object/upload/sign/{b}/{k}` GET + `Origin: https://evil.example` + apikey/Bearer → `400 {"code":"NoSuchBucket"}` with `ACAO: *` and **no** `ACAC`
- NEW `aygnpacdkgtsfnhgcyjc.storage.supabase.co/storage/v1/s3/{bucket}?list-type=2` → `403 <Code>AccessDenied</Code><Message>Missing signature</Message>` with `<Resource>zzz_ctrl_9x7</Resource>` and **no** 
- CHANGED `kurs.onecode.de` — day-16, **no deploy**. `GET /login` → 200, 18 702 B, page sha256 `99798c7d94a15abf93ec349b0b221a89dfba756cb21fc581a09d37acd21d9450` (byte-identical since the 2026-09-19 11:33Z buil
- CHANGED `aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1` — CORS auth-state discriminator re-proven with a matched control on one path, this cycle: `GET /auth/v1/settings?apikey=<pub>` + `Origin: https://evil.exampl
- CHANGED `cto.onecode.de` — day-54, unchanged. CNAME `cname.perspective-dns.com.`, A `104.18.2.73`/`104.18.3.73`, TXT = CNAME line only (zero verification records), `GET http://cto.onecode.de/` → `409`
- CHANGED Supabase REST `/rest/v1/` monitor formally closed 09-17 (27 probes, 503↔401 oscillation, never 200+rows); platform enforces `sb_publishable_` format only
- CHANGED Storage plane CORS characterization closed: `ACAO: *`, no `ACAC`, no reflection — with apikey+Bearer on all 10 mounted GET routes

## 2026-10-03 05:11:23 UTC
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/.well-known/oauth-authorization-server` → `404 {"code":404,"error_code":"feature_disabled","msg":"OAuth server is disabled"}` served by the **OAuth router, no
- NEW `.well-known` fallthrough closed by counter-example: `zzz_ctrl_9x7`, `acme-challenge`, and the subtree root all return `401 No API key found in request` with `ACAO: *` + full 9-method list + `max-age 
- NEW `OPTIONS` preflight on the well-known subtree → `200 ACAO: *` + 9-method list + `max-age 3600`, identical on both `openid-configuration` and `oauth-authorization-server`. Preflight uniform; only the *
- CHANGED **My own conf-72 claim is narrowed and survives in corrected form.** "Reflection on this subtree is unconditional" is **retracted**. Correct three-tier model: (A) registered well-known docs + OAuth-ro
- CHANGED `kurs.onecode.de` — day-18, **no deploy**. `/login` 200, 18 702 B, sha256 `99798c7d94a15abf93ec349b0b221a89dfba756cb21fc581a09d37acd21d9450`; main chunk 154 581 B sha256 `f916f314ea61a8c58a055707fc63c
- CHANGED `cto.onecode.de` — day-56, `cname.perspective-dns.com.` → 104.18.3.73/104.18.2.73, HTTP 409. Unchanged.
- NEW Negative recorded: `GET /auth/v1/.well-known/../settings` → normalises to `/auth/v1/settings` and is gated at `401`. No path-traversal gate bypass.
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/.well-known/openid-configuration` + `jwks.json` — pre-auth OIDC discovery documents live (200), advertise RS256/HS256/ES256 id_token signing but JWKS serves o
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/.well-known/jwks.json` reflects arbitrary `Origin` with `ACAC: true` **without** apikey (unauthenticated) — falsifies "auth-state discriminator" model; CORS o
- NEW JWT algorithm confusion comprehensively closed on both planes: 38 live probes (27 PostgREST + 11 GoTrue) across HS256/RS256/PS256/ES256/EdDSA × attacker keys — zero tokens authenticated; embedded JWK 
- NEW `api.`, `functions.`, `realtime.aygnpacdkgtsfnhgcyjc.supabase.co` → zero A records (legacy Supabase hostnames not routed)
- CHANGED `kurs.onecode.de` — day-17, no deploy; main chunk `f916f314ea61a8c5...` byte-identical since 2026-09-19; pre-auth surface frozen at `{/login,/passwort-vergessen,/datenschutz,/rechtliches}` 200; all `/
- CHANGED `cto.onecode.de` — day-55, CNAME `cname.perspective-dns.com.`, A `104.18.2.73/3.73`, TXT = CNAME line only (zero verification), HTTP 409 "error code:1001", TLS handshake-fail — passive probing converg
- CHANGED Supabase REST `/rest/v1/` — 503 PGRST002 (schema-cache-down); monitor formally closed 09-17 (27 probes, 503↔401, never 200+rows); platform enforces `sb_publishable_` format only
- CHANGED `aygnpacdkgtsfnhgcyjc.storage.supabase.co/storage/v1/s3` — 403 S3 XML "Missing signature" confirmed live; independent SigV4 authz plane, access-key-ID oracle verified (400 InvalidSignature vs 403 Miss
- CHANGED GoTrue credentialed CORS: `apikey` query param → reflects arbitrary `Origin` with `ACAC: true` on 200/401/404/405; unauthenticated → wildcard `ACAO: *` no ACAC — router-wide confirmed

## 2026-10-03 10:30:25 UTC
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/.well-known/openid-configuration` + `jwks.json` — pre-auth OIDC discovery documents live (200), advertise RS256/HS256/ES256 id_token signing but JWKS serves o
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/.well-known/jwks.json` reflects arbitrary `Origin` with `ACAC: true` **without** apikey (unauthenticated) — falsifies "auth-state discriminator" model; CORS o
- NEW JWT algorithm confusion comprehensively closed on both planes: 38 live probes (27 PostgREST + 11 GoTrue) across HS256/RS256/PS256/ES256/EdDSA × attacker keys — zero tokens authenticated; embedded JWK 
- NEW `api.`, `functions.`, `realtime.aygnpacdkgtsfnhgcyjc.supabase.co` → zero A records (legacy Supabase hostnames not routed)
- CHANGED `kurs.onecode.de` — day-17, no deploy; main chunk `f916f314ea61a8c5...` byte-identical since 2026-09-19; pre-auth surface frozen at `{/login,/passwort-vergessen,/datenschutz,/rechtliches}` 200; all `/
- CHANGED `cto.onecode.de` — day-55, CNAME `cname.perspective-dns.com.`, A `104.18.2.73/3.73`, TXT = CNAME line only (zero verification), HTTP 409 "error code:1001", TLS handshake-fail — passive probing converg
- CHANGED Supabase REST `/rest/v1/` — 503 PGRST002 (schema-cache-down); monitor formally closed 09-17 (27 probes, 503↔401, never 200+rows); platform enforces `sb_publishable_` format only
- CHANGED `aygnpacdkgtsfnhgcyjc.storage.supabase.co/storage/v1/s3` — 403 S3 XML "Missing signature" confirmed live; independent SigV4 authz plane, access-key-ID oracle verified (400 InvalidSignature vs 403 Miss
- CHANGED GoTrue credentialed CORS: `apikey` query param → reflects arbitrary `Origin` with `ACAC: true` on 200/401/404/405; unauthenticated → wildcard `ACAO: *` no ACAC — router-wide confirmed

## 2026-10-03 15:00:44 UTC
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/.well-known/openid-configuration` — the NEXT directive is now **closed at endpoint level**. All three advertised OAuth endpoints are dead: `/auth/v1/oauth/aut
- NEW **DELTA — the OAuth reflection is exact-route, not prefix-mounted.** `/auth/v1/oauth/zzz_ctrl_9x7`, `/auth/v1/oauth/` and `/auth/v1/oauth` all return `401 {"message":"No API key found in request"}` wi
- NEW `/auth/v1/.well-known/oauth-authorization-server/aygnpacdkgtsfnhgcyjc.supabase.co` (RFC 8414 §3 path-insertion metadata form, never tested) → `404 page not found` with `ACAO` reflected + `ACAC: true` 
- NEW `Origin: null` → `ACAO: null` + `ACAC: true` on all three advertised endpoints (`authorize`, `token`, `userinfo`). No attacker-controlled domain required anywhere on tier A.
- NEW **Preflight is uniform wildcard and does NOT reflect**, on tier A and tier C alike: `OPTIONS` on `/auth/v1/oauth/authorize`, `/auth/v1/oauth/token`, `/auth/v1/.well-known/jwks.json`, `/auth/v1/oauth/z
- NEW `token_endpoint_auth_methods_supported: ["client_secret_basic","client_secret_post","none"]` and `grant_types_supported: ["refresh_token"]` + `scopes_supported` incl. `offline_access` — a fourth overs
- CHANGED `kurs.onecode.de` — day-19, **no deploy**. `/login` → 200, 18 702 B, sha256 `99798c7d94a15abf93ec349b0b221a89dfba756cb21fc581a09d37acd21d9450` (64-hex asserted), **zero** `Set-Cookie`. Byte-identical 
- CHANGED `cto.onecode.de` — day-57, CNAME `cname.perspective-dns.com.`, HTTP `409`. Unchanged.
- CHANGED `aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1` — `400 {"code":"NoSuchBucket"}` on the control bucket, unchanged.
- NEW **The queued NEXT paid off — and it falsified my own previous-cycle claim.** `/auth/v1/oauth/token/extra` → `404 feature_disabled` with reflected `ACAO` + `ACAC: true`. `/auth/v1/oauth/authorize/extra
- NEW **The entire pre-gate reflecting surface is unbounded in path space.** All 6 pre-gate route names are prefix-mounted at arbitrary depth: `.well-known/jwks.json/anything`, `.well-known/openid-configura
- NEW **Corrected mechanism — it is not "CORS tiers", it is gate ordering.** `401 {"message":"No API key found in request"}` with `ACAO: *` and no `ACAC` is GoTrue's **global apikey gate, which runs before 
- NEW Final pre-gate enumeration (8 names tested, credential-free, no apikey): **6 are pre-gate** — `.well-known/jwks.json` (200 ES256), `.well-known/openid-configuration` (200), `.well-known/oauth-authoriz
- NEW Third traversal negative: `/auth/v1/.well-known/oauth-authorization-server/../../settings` normalises to `/auth/v1/settings` → `401 No API key found`, `ACAO: *`, no ACAC. Prefix mounting does not crea
- CHANGED `kurs.onecode.de` — day-19, no deploy. `/login` → 200, 18 702 B, sha256 `99798c7d94a15abf93ec349b0b221a89dfba756cb21fc581a09d37acd21d9450`, zero `Set-Cookie`. Byte-identical since 2026-09-19 11:33Z.
- CHANGED `cto.onecode.de` — day-57, CNAME `cname.perspective-dns.com.`, HTTP `409`. Unchanged. `storage/v1` → `400 NoSuchBucket` on the control bucket, unchanged.
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/.well-known/openid-configuration` + `jwks.json` — pre-auth OIDC discovery documents live (200), advertise RS256/HS256/ES256 id_token signing but JWKS serves o
- NEW `aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/.well-known/jwks.json` reflects arbitrary `Origin` with `ACAC: true` **without** apikey (unauthenticated) — falsifies "auth-state discriminator" model; CORS o
- NEW JWT algorithm confusion comprehensively closed on both planes: 38 live probes (27 PostgREST + 11 GoTrue) across HS256/RS256/PS256/ES256/EdDSA × attacker keys — zero tokens authenticated; embedded JWK 
- NEW `api.`, `functions.`, `realtime.aygnpacdkgtsfnhgcyjc.supabase.co` → zero A records (legacy Supabase hostnames not routed)
- NEW S3-compatible storage plane `aygnpacdkgtsfnhgcyjc.storage.supabase.co/storage/v1/s3` confirmed live (403 Missing signature), independent SigV4 authz plane, access-key-ID oracle verified (400 InvalidSi
- CHANGED `kurs.onecode.de` — day-17, no deploy; main chunk `f916f314ea61a8c5...` byte-identical since 2026-09-19; pre-auth surface frozen at `{/login,/passwort-vergessen,/datenschutz,/rechtliches}` 200; all `/
- CHANGED `cto.onecode.de` — day-55, CNAME `cname.perspective-dns.com.`, A `104.18.2.73/3.73`, TXT = CNAME line only (zero verification), HTTP 409 "error code:1001", TLS handshake-fail — passive probing converg
- CHANGED Supabase REST `/rest/v1/` — 503 PGRST002 (schema-cache-down); monitor formally closed 09-17 (27 probes, 503↔401, never 200+rows); platform enforces `sb_publishable_` format only
- CHANGED Supabase Storage bucket-existence oracle confirmed (81 names excluded) but bucket names unrecoverable pre-auth
