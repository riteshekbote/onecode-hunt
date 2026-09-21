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
