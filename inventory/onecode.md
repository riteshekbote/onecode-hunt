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
