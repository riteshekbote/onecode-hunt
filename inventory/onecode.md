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
