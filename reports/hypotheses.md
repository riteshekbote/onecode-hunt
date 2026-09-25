# Hypotheses (ranked)

## RANKED HYPOTHESES 2026-09-02 21:41:05 UTC

## RANKED HYPOTHESES 2026-09-02 23:34:10 UTC

## RANKED HYPOTHESES 2026-09-03 01:27:20 UTC

## RANKED HYPOTHESES 2026-09-03 06:31:56 UTC

## RANKED HYPOTHESES 2026-09-03 11:43:43 UTC

## RANKED HYPOTHESES 2026-09-03 16:16:20 UTC
- [65] kurs.onecode.de: Railway-hosted auth bypass via session fixation on kurs.onecode.de (from art/lead_nemotron3.txt)
- [40] kurs.onecode.de: Railway app API discovery (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://kurs.onecode.de/api/ HEAD (expect 301/302/401/403/200)
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://kurs.onecode.de/login — capture Set-Cookie headers, response body (CSRF token, form structure), security headers (CSP, HSTS, X-Frame-Options)
- LEARN: REJECTED XSS/IDOR/SSRF/OATH @ api: no endpoints identified yet
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: confidence below threshold (45), passive-only verification cannot confirm takeover without active DNS resoluti
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Railway-hosted apps with 307 login redirect are high-value for session fixation/IDOR; tech_exposure=8 (Railway, auth flow, like
- LEARN: ACCEPTED IDOR @ kurs.onecode.de: Course platform semantics (enrollments, resources) strongly predict IDOR; gate_ease=9 (login required but test account feasible

## RANKED HYPOTHESES 2026-09-03 19:28:15 UTC
- [65] kurs.onecode.de: Session fixation via pre-auth cookie reuse on Railway-hosted kurs.onecode.de (from art/lead_nemotron3.txt)
- [65] kurs.onecode.de: Session fixation on Railway-hosted kurs.onecode.de (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://kurs.onecode.de/login — capture Set-Cookie headers, response body (CSRF token, form structure), security headers (CSP, HSTS, X-Frame-Options)
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://kurs.onecode.de/login — capture Set-Cookie headers, response body (CSRF token, form structure), security headers (CSP, HSTS, X-Frame-Options)
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Railway-hosted apps with 307 login redirect are high-value for session fixation/IDOR; tech_exposure=8 (Railway, auth flow, like
- LEARN: ACCEPTED IDOR @ kurs.onecode.de: Course platform semantics (enrollments, resources) strongly predict IDOR; gate_ease=9 (login required but test account feasible
- LEARN: REJECTED XSS/IDOR/SSRF/OATH @ api: no endpoints identified yet
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: confidence below threshold (45), passive-only verification cannot confirm takeover without active DNS resoluti
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Railway-hosted apps with 307 login redirect are high-value for session fixation/IDOR; tech_exposure=8 (Railway, auth flow, like
- LEARN: ACCEPTED IDOR @ kurs.onecode.de: Course platform semantics (enrollments, resources) strongly predict IDOR; gate_ease=9 (login required but test account feasible
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface (from bigpickle).

## RANKED HYPOTHESES 2026-09-03 21:54:04 UTC
- [65] kurs.onecode.de: Session fixation on Railway-hosted kurs.onecode.de (from art/lead_bigpickle.txt)
- [60] kurs.onecode.de: Session fixation via pre-auth cookie reuse on Railway-hosted kurs.onecode.de (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: POST https://kurs.onecode.de/login — with test credentials (if available) to capture Set-Cookie headers, session ID regeneration behavior, cookie attribu
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://kurs.onecode.de/login — capture Set-Cookie headers, response body (CSRF token, form structure), security headers (CSP, HSTS, X-Frame-Options)
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Railway-hosted Next.js app with 307 login redirect confirmed; tech_exposure=8 (Railway, Next.js, auth flow, likely API surface)
- LEARN: ACCEPTED IDOR @ kurs.onecode.de: Course platform semantics confirmed (Rich Dev Poor Dev, invite-only, dashboard/enrollments); gate_ease=9 (test account feasible
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app has API surface (all /api/*, /graphql, /dashboard gated by 307).
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: confidence below threshold (45), passive-only verification cannot confirm takeover without active DNS resoluti
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Railway-hosted apps with 307 login redirect are high-value for session fixation/IDOR; tech_exposure=8 (Railway, auth flow, like
- LEARN: ACCEPTED IDOR @ kurs.onecode.de: Course platform semantics (enrollments, resources) strongly predict IDOR; gate_ease=9 (login required but test account feasible
- LEARN: REJECTED XSS/IDOR/SSRF/OATH @ api: no endpoints identified yet
- LEARN: REJECTED XSS/IDOR/SSRF/OATH @ api: no endpoints identified yet
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Railway-hosted apps with 307 login redirect are high-value for session fixation/IDOR; tech_exposure=8 (Railway, auth flow, like
- LEARN: ACCEPTED IDOR @ kurs.onecode.de: Course platform semantics (enrollments, resources) strongly predict IDOR; gate_ease=9 (login required but test account feasible
- LEARN: REJECTED XSS/IDOR/SSRF/OATH @ api: no endpoints identified yet
- LEARN: REJECTED XSS/IDOR/SSRF/OATH @ api: no endpoints identified yet
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Railway-hosted apps with 307 login redirect are high-value for session fixation/IDOR; tech_exposure=8 (Railway, auth flow, like
- LEARN: ACCEPTED IDOR @ kurs.onecode.de: Course platform semantics (enrollments, resources) strongly predict IDOR; gate_ease=9 (login required but test account feasible
- LEARN: REJECTED XSS/IDOR/SSRF/OATH @ api: no endpoints identified yet
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: confirmed Next.js/Turbopack App Router with registered /api + /v1 routes (auth-gated) -> post-auth BOLA surface real.
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: no pre-auth session cookie; Next.js session gate on all routes; session-fixation pre-auth mechanism unsupported.
- LEARN: REJECTED IDOR(pre-auth) @ api: no pre-auth endpoints found; only post-auth BOLA testable which needs account.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: registered /api,/v1 routers + course semantics => BOLA chain plausible; gate_ease=LOW (invite-only).
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Railway-hosted apps with 307 login redirect are high-value for session fixation/IDOR; tech_exposure=8 (Railway, auth flow, like
- LEARN: ACCEPTED IDOR @ kurs.onecode.de: Course platform semantics (enrollments, resources) strongly predict IDOR; gate_ease=9 (login required but test account feasible
- LEARN: REJECTED XSS/IDOR/SSRF/OATH @ api: no endpoints identified yet
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: confirmed Next.js/Turbopack App Router with registered /api + /v1 routes (auth-gated) -> post-auth BOLA surface real.
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: no pre-auth session cookie; Next.js session gate on all routes; session-fixation pre-auth mechanism unsupported.
- LEARN: REJECTED IDOR(pre-auth) @ api: no pre-auth endpoints found; only post-auth BOLA testable which needs account.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: registered /api,/v1 routers + course semantics => BOLA chain plausible; gate_ease=LOW (invite-only).

## RANKED HYPOTHESES 2026-09-04 00:01:14 UTC
- [65] kurs.onecode.de: Post-auth BOLA/IDOR on course enrollment via /api/v1 routes (from art/lead_nemotron3.txt)
- [62] kurs.onecode.de: Post-auth BOLA via Supabase RLS policy gaps on authenticated resources (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: obtain two invited test accounts for kurs.onecode.de (invite-only) to test post-auth BOLA on /api/courses|resources|enrollments + cross-account Supabase 
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://kurs.onecode.de/api/auth/providers — check for NextAuth.js unauthenticated provider config endpoint (common in Next.js apps) to enumerate aut
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: auth stack = Supabase (project aygnpacdkgtsfnhgcyjc, publishable key sha256 870cf518...); email-only, signup disabled, confirma
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: no unauthenticated Supabase REST/table exposure (PGRST002 503); anon-REST enumeration not viable.
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: recovery/invite use Supabase magic-link with session tokens in URL fragment; redirect locked to fixed whitelist {invite:/einlad
- LEARN: REJECTED OATH @ kurs.onecode.de: no external OAuth providers configured (all false in /auth/v1/settings) => OAuth redirect_uri/state attack surface minimal.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: backend = single Supabase project; UUID PKs weaken guessable-ID BOLA, so realistic high-value target is missing RLS 
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Railway-hosted Next.js app with 307 login redirect confirmed; tech_exposure=8 (Railway, Next.js, auth flow, likely API surface)
- LEARN: ACCEPTED IDOR @ kurs.onecode.de: Course platform semantics confirmed (Rich Dev Poor Dev, invite-only, dashboard/enrollments); gate_ease=9 (test account feasible
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app has API surface (all /api/*, /graphql, /dashboard gated by 307).
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: confirmed Next.js/Turbopack App Router with registered /api + /v1 routes (auth-gated) -> post-auth BOLA surface real.
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: no pre-auth session cookie; Next.js session gate on all routes; session-fixation pre-auth mechanism unsupported.
- LEARN: REJECTED IDOR(pre-auth) @ api: no pre-auth endpoints found; only post-auth BOLA testable which needs account.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: registered /api,/v1 routers + course semantics => BOLA chain plausible; gate_ease=LOW (invite-only).
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: confidence below threshold (45), passive-only verification cannot confirm takeover without active DNS resoluti
- LEARN: REJECTED XSS/IDOR/SSRF/OATH @ api: no endpoints identified yet.

## RANKED HYPOTHESES 2026-09-04 03:59:02 UTC
- [65] kurs.onecode.de: Post-auth BOLA via Supabase RLS policy gap across tenants (from art/lead_nemotron3.txt)
- [62] kurs.onecode.de: Post-auth cross-tenant BOLA via missing Supabase RLS policy filter (from art/lead_bigpickle.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Obtain two invited test accounts for kurs.onecode.de (invite-only) to test post-auth BOLA on `/api/courses|resources|enrollments` + cross-account Supabas
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Auth stack = Supabase (project aygnpacdkgtsfnhgcyjc, publishable key sha256 870cf518...); email-only, signup disabled, confirma
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: No unauthenticated Supabase REST/table exposure (PGRST002 503); anon-REST enumeration not viable.
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Recovery/invite use Supabase magic-link with session tokens in URL fragment; redirect locked to fixed whitelist {invite:/einlad
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings) => OAuth redirect_uri/state attack surface minimal.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Backend = single Supabase project; UUID PKs weaken guessable-ID BOLA, so realistic high-value target is missing RLS 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Confirmed Next.js/Turbopack App Router with registered /api + /v1 routes (auth-gated) -> post-auth BOLA surface real.
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: No pre-auth session cookie; Next.js session gate on all routes; session-fixation pre-auth mechanism unsupported.
- LEARN: REJECTED IDOR(pre-auth) @ api: No pre-auth endpoints found; only post-auth BOLA testable which needs account.
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Realtime /api/broadcast channel endpoint identified in client bundle; 307 pre-auth, post-auth channel-auth gap possible.
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence below threshold (45), passive-only verification cannot confirm takeover without active DNS resoluti
- LEARN: REJECTED XSS/IDOR/SSRF/OATH @ api: No endpoints identified yet.

## RANKED HYPOTHESES 2026-09-04 08:47:33 UTC
- [65] kurs.onecode.de: Post-auth BOLA via Supabase RLS policy gap across tenants (from art/lead_nemotron3.txt)
- [55] aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Supabase Storage public bucket exposure (from art/lead_bigpickle.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Obtain two invited test accounts for kurs.onecode.de (invite-only) to test post-auth BOLA on `/api/courses|resources|enrollments` + cross-account Supabas
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket with `Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsI
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Auth stack = Supabase (project aygnpacdkgtsfnhgcyjc, publishable key sha256 870cf518...); email-only, signup disabled, confirma
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: No unauthenticated Supabase REST/table exposure (PGRST002 503); anon-REST enumeration not viable.
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Recovery/invite use Supabase magic-link with session tokens in URL fragment; redirect locked to fixed whitelist {invite:/einlad
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings) => OAuth redirect_uri/state attack surface minimal.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Backend = single Supabase project; UUID PKs weaken guessable-ID BOLA, so realistic high-value target is missing RLS 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Confirmed Next.js/Turbopack App Router with registered /api + /v1 routes (auth-gated) -> post-auth BOLA surface real.
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: No pre-auth session cookie; Next.js session gate on all routes; session-fixation pre-auth mechanism unsupported.
- LEARN: REJECTED IDOR(pre-auth) @ api: No pre-auth endpoints found; only post-auth BOLA testable which needs account.
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Realtime /api/broadcast channel endpoint identified in client bundle; 307 pre-auth, post-auth channel-auth gap possible.
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence below threshold (45), passive-only verification cannot confirm takeover without active DNS resoluti
- LEARN: REJECTED XSS/IDOR/SSRF/OATH @ api: No endpoints identified yet.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Supabase Storage service endpoint exists and is NOT behind Next.js middleware; directly acces
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Supabase Edge Functions endpoint may exist and is NOT behind app auth middleware; deployed 
- LEARN: REJECTED AUTH @ kurs.onecode.de: Pre-auth surface fully exhausted (only /login and /passwort-vergessen at 200); all other routes 307→/login; no further pre-auth
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value hypothesis (conf 62-65); requires two invited test account

## RANKED HYPOTHESES 2026-09-04 13:36:00 UTC
- [58] aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Supabase Storage public bucket listing (from art/lead_bigpickle.txt)
- [55] aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Supabase Storage public bucket exposure (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket with Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsIn
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket with `Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsI
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with anon key — public bucket exposure 
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Edge Functions may exist without auth — probeable.
- LEARN: REJECTED AUTH @ kurs.onecode.de: Pre-auth surface fully exhausted — only /login and /passwort-vergessen at 200.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap highest value (conf 62-65) — requires test accounts.
- LEARN: REJECTED Realtime (conf 35): speculative without live probe — parked below threshold.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Supabase Storage service endpoint exists and is NOT behind Next.js middleware; directly acces
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Supabase Edge Functions endpoint may exist and is NOT behind app auth middleware; deployed 
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value hypothesis (conf 62-65); requires two invited test account
- LEARN: REJECTED AUTH @ kurs.onecode.de: Pre-auth surface fully exhausted (only /login and /passwort-vergessen at 200); all other routes 307→/login; no further pre-auth
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings) => OAuth redirect_uri/state attack surface minimal.
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence below threshold (45), passive-only verification cannot confirm takeover without active DNS resoluti
- LEARN: REJECTED XSS/IDOR/SSRF/OATH @ api: No endpoints identified yet.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Supabase Storage service endpoint exists and is NOT behind Next.js middleware; directly acces
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Supabase Edge Functions endpoint may exist and is NOT behind app auth middleware; deployed 
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value hypothesis (conf 62-65); requires two invited test account
- LEARN: REJECTED AUTH @ kurs.onecode.de: Pre-auth surface fully exhausted (only /login and /passwort-vergessen at 200); all other routes 307→/login; no further pre-auth
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings) => OAuth redirect_uri/state attack surface minimal.
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence below threshold (45), passive-only verification cannot confirm takeover without active DNS resoluti
- LEARN: REJECTED XSS/IDOR/SSRF/OATH @ api: No endpoints identified yet.

## RANKED HYPOTHESES 2026-09-04 17:14:36 UTC
- [65] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Post-auth BOLA via Supabase RLS gap (from art/lead_bigpickle.txt)
- [55] aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Supabase Storage public bucket exposure (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket with `Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsI
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Supabase Storage service endpoint exists and is NOT behind Next.js middleware; directly acces
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Supabase Edge Functions endpoint may exist and is NOT behind app auth middleware; deployed 
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value hypothesis (conf 62-65); requires two invited test account
- LEARN: REJECTED AUTH @ kurs.onecode.de: Pre-auth surface fully exhausted (only /login and /passwort-vergessen at 200); all other routes 307→/login; no further pre-auth
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings) => OAuth redirect_uri/state attack surface minimal.
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence below threshold (45), passive-only verification cannot confirm takeover without active DNS resoluti
- LEARN: REJECTED XSS/IDOR/SSRF/OATH @ api: No endpoints identified yet.

## RANKED HYPOTHESES 2026-09-04 20:01:49 UTC
- [58] aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Supabase Storage public bucket listing (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket with Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsIn
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with anon key — public bucket exposure 
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Edge Functions may exist without auth — probeable.
- LEARN: REJECTED AUTH @ kurs.onecode.de: Pre-auth surface fully exhausted — only /login and /passwort-vergessen at 200.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap highest value (conf 62-65) — requires test accounts.
- LEARN: REJECTED Realtime (conf 35): speculative without live probe — parked below threshold.

## RANKED HYPOTHESES 2026-09-04 22:27:30 UTC
- [40] aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Supabase Edge Functions undeployed or unlistable (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): SCAN: Enumerate kurs.onecode.de post-auth API surface via JS bundle route extraction — find all /api/* and /v1/* route handlers in client chunks to map BOLA tar
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm takeover without active DNS resolution

## RANKED HYPOTHESES 2026-09-05 00:17:17 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_bigpickle.txt)
- [65] kurs.onecode.de: Post-auth BOLA via Supabase RLS policy gap across course tenants (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with headers `apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30` and 
- NEXT(hypotheses-nemotron3.txt): SCAN: Enumerate `kurs.onecode.de` post-auth API surface via JS bundle route extraction — find all `/api/*` and `/v1/*` route handlers in client chunks to map BO
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm takeover without active DNS resolution

## RANKED HYPOTHESES 2026-09-05 04:43:56 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): SCAN: Enumerate `kurs.onecode.de` post-auth API surface via JS bundle route extraction — find all `/api/*` and `/v1/*` route handlers in client chunks to map BO
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm takeover without active DNS resolution

## RANKED HYPOTHESES 2026-09-05 08:46:23 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Escalate to obtain two invited test accounts for the RLS-gap BOLA (65) and GraphQL introspection (48) hypotheses. Without accounts, pre-auth surface is e
- NEXT(hypotheses-nemotron3.txt): SCAN: Enumerate `kurs.onecode.de` post-auth API surface via JS bundle route extraction — find all `/api/*` and `/v1/*` route handlers in client chunks to map BO
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm takeover without active DNS resolution
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm takeover without active DNS resolution

## RANKED HYPOTHESES 2026-09-05 12:11:29 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via missing Supabase RLS filter (from art/lead_bigpickle.txt)
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): SCAN: Enumerate `kurs.onecode.de` post-auth API surface via JS bundle route extraction — find all `/api/*` and `/v1/*` route handlers in client chunks to map BO
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm takeover without active DNS resolution

## RANKED HYPOTHESES 2026-09-05 15:42:43 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via missing Supabase RLS filter (from art/lead_bigpickle.txt)
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Escalate to obtain two invited test accounts for the RLS-gap BOLA (conf 65) hypothesis. Without accounts, pre-auth surface is exhausted and post-auth tes
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm takeover without active DNS resolution
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm takeover without active DNS resolution

## RANKED HYPOTHESES 2026-09-05 17:42:22 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- [50] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Publishable-key direct REST exposure on schema-cache recovery (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Escalate to obtain two invited test accounts to activate the post-auth RLS-gap BOLA (conf 65) hypothesis; pre-auth surface fully exhausted and the only r
- NEXT(hypotheses-nemotron3.txt): HUMAN: Escalate to obtain two invited test accounts for the RLS-gap BOLA (conf 65) hypothesis. Without accounts, pre-auth surface is exhausted and post-auth tes
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Probed again 2026-09-05 → 503 PGRST002 with publishable key; schema-cache still down, no anon ta
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface still exhausted (/login 200 only).
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1: Probed again → 503 (cache block, same as REST); no pre-auth introspection possible.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm takeover without active DNS resolution

## RANKED HYPOTHESES 2026-09-05 19:35:48 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- [50] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Publishable-key direct REST exposure on schema-cache recovery (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Escalate to obtain two invited test accounts for kurs.onecode.de to activate the post-auth BOLA hypothesis (conf 65, CRITICAL impact). Pre-auth surface i
- NEXT(hypotheses-nemotron3.txt): HUMAN: Escalate to obtain two invited test accounts for the RLS-gap BOLA (conf 65) hypothesis. Without accounts, pre-auth surface is exhausted and post-auth tes
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Probed again 2026-09-05 → 503 PGRST002 with publishable key; schema-cache still down, no anon ta
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface still exhausted (/login 200 only).
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1: Probed again → 503 (cache block, same as REST); no pre-auth introspection possible.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Empty bucket list confirmed again — endpoint probeable but zero buckets exist.
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404 — no deployed functions.
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401 — auth required.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm takeover without active DNS resolution

## RANKED HYPOTHESES 2026-09-05 21:48:33 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- [52] cto.onecode.de: Dangling Cloudflare-proxied CNAME on cto.onecode.de (error 1001) (from art/lead_bigpickle.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Escalate to obtain two invited test accounts for kurs.onecode.de to activate the post-auth BOLA hypothesis (conf 65, CRITICAL impact). Pre-auth surface i
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Probed again 2026-09-05 → 503 PGRST002 with publishable key; schema-cache still down, no anon ta
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1: Probed again → 503 (cache block, same as REST); no pre-auth introspection possible
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm takeover without active DNS resolution

## RANKED HYPOTHESES 2026-09-05 23:43:03 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- [58] cto.onecode.de: Dangling Perspective CNAME takeover on cto.onecode.de (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Create a Perspective account and attempt to bind custom subdomain cto.onecode.de (CNAME already resolves to cname.perspective-dns.com) — if attacker cont
- NEXT(hypotheses-nemotron3.txt): HUMAN: Escalate to obtain two invited test accounts for kurs.onecode.de to activate the post-auth BOLA hypothesis (conf 65, CRITICAL impact). Pre-auth surface i
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: Provider identified — cname.perspective-dns.com = Perspective funnel SaaS custom-subdomain CNAME target (docs-confirmed); s
- LEARN: REJECTED MISCONFIG @ www.onecode.de: static Webflow marketing, CF-cached HIT, no dynamic surface — no delta from runs 09-02..09-05.
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: 95.130.17.37 no HTTP; non-web (mail) — out-of-scope class, no action.
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface still exhausted (/login, /passwort-vergessen only; all /api,/v1,/dashboard 307); no change 09-05.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 503 PGRST002 as of 09-05; next monitor due <=09-06 (once/day).
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Probed again 2026-09-05 → 401 "Secret API key required" with publishable key; schema-cache down 
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1: Probed again → 503 (cache block, same as REST); no pre-auth introspection possible
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: REJECTED MISCONFIG @ cto.onecode.de/hostmaster.*: Confidence 45 < 50; passive-only cannot confirm takeover without active DNS resolution

## RANKED HYPOTHESES 2026-09-06 03:58:05 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Escalate to obtain two invited test accounts for kurs.onecode.de to activate the post-auth BOLA hypothesis (conf 65, CRITICAL impact). Pre-auth surface e
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Probed again 2026-09-05 → 401 "Secret API key required" with publishable key; schema-cache down 
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1: Probed again → 503 (cache block, same as REST); no pre-auth introspection possible
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: Provider identified — cname.perspective-dns.com = Perspective funnel SaaS custom-subdomain CNAME target (docs-confirmed); s
- LEARN: REJECTED MISCONFIG @ www.onecode.de: static Webflow marketing, CF-cached HIT, no dynamic surface — no delta from runs 09-02..09-05
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: 95.130.17.37 no HTTP; non-web (mail) — out-of-scope class, no action
- LEARN: REJECTED MISCONFIG @ cto.onecode.de/hostmaster.*: Confidence 45 < 50; passive-only cannot confirm takeover without active DNS resolution

## RANKED HYPOTHESES 2026-09-06 08:40:13 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via missing Supabase RLS filter (from art/lead_bigpickle.txt)
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Create a Perspective account and attempt to bind custom subdomain cto.onecode.de (CNAME already resolves to cname.perspective-dns.com) — if attacker cont
- NEXT(hypotheses-nemotron3.txt): HUMAN: Escalate to obtain two invited test accounts for kurs.onecode.de to activate the post-auth BOLA hypothesis (conf 65, CRITICAL impact). Pre-auth surface e
- LEARN: NO_DELTA @ all: REST 401 anon-block persists; cto 409/1001 persists; storage empty; GraphQL 503 PGRST002 persists; kurs.onecode.de/login 200 unchanged. No state
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: Provider confirmed as Perspective funnel SaaS; stable 409/1001 + missing cert = hostname unbound and reclaimable (conf 58, 
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires two invited test accounts.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Explicit 401 anon-block with publishable key; monitor for cache recovery.
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured.
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface.
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope.
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Probed again 2026-09-05 → 401 "Secret API key required" with publishable key; schema-cache down 
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1: Probed again → 503 (cache block, same as REST); no pre-auth introspection possible
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: Provider identified — cname.perspective-dns.com = Perspective funnel SaaS custom-subdomain CNAME target (docs-confirmed); s
- LEARN: REJECTED MISCONFIG @ www.onecode.de: static Webflow marketing, CF-cached HIT, no dynamic surface — no delta from runs 09-02..09-05
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: 95.130.17.37 no HTTP; non-web (mail) — out-of-scope class, no action
- LEARN: REJECTED MISCONFIG @ cto.onecode.de/hostmaster.*: Confidence 45 < 50; passive-only cannot confirm takeover without active DNS resolution

## RANKED HYPOTHESES 2026-09-06 12:22:06 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via missing Supabase RLS filter (from art/lead_bigpickle.txt)
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Escalate to obtain two invited test accounts for kurs.onecode.de to activate the post-auth BOLA hypothesis (conf 65, CRITICAL impact). Pre-auth surface e
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Probed again 2026-09-05 → 401 "Secret API key required" with publishable key; schema-cache down 
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1: Probed again → 503 (cache block, same as REST); no pre-auth introspection possible
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: Provider identified — cname.perspective-dns.com = Perspective funnel SaaS custom-subdomain CNAME target (docs-confirmed); s
- LEARN: REJECTED MISCONFIG @ www.onecode.de: static Webflow marketing, CF-cached HIT, no dynamic surface — no delta from runs 09-02..09-05
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: 95.130.17.37 no HTTP; non-web (mail) — out-of-scope class, no action
- LEARN: REJECTED MISCONFIG @ cto.onecode.de/hostmaster.*: Confidence 45 < 50; passive-only cannot confirm takeover without active DNS resolution

## RANKED HYPOTHESES 2026-09-06 15:39:14 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via missing Supabase RLS filter (from art/lead_bigpickle.txt)
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Create a Perspective funnel account, attach custom subdomain cto.onecode.de (CNAME already targets cname.perspective-dns.com) and observe whether attacke
- NEXT(hypotheses-nemotron3.txt): HUMAN: Escalate to obtain two invited test accounts for kurs.onecode.de to activate the post-auth BOLA hypothesis (conf 65, CRITICAL impact). Pre-auth surface e
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME → cname.perspective-dns.com stable (dig 09-06), 409/1001 + missing cert → hostname unbound and reclaimable; conf 58, 
- LEARN: REJECTED MISCONFIG @ hostmaster.onecode.de: NXDOMAIN (no A/CNAME) in onecode's controlled zone → not claimable; differs from cto's live provider-CNAME class.
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login HEAD 200 unchanged; pre-auth surface stable; no new session/cookie signal.
- LEARN: NO_DELTA @ all: same-day monitor run — no state change vs 09-06 12:22; REST/recovery re-probe deferred to <=00:00Z 09-07 per <=1/day cadence.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Probed again 2026-09-05 → 401 "Secret API key required" with publishable key; schema-cache down 
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1: Probed again → 503 (cache block, same as REST); no pre-auth introspection possible
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: Provider identified — cname.perspective-dns.com = Perspective funnel SaaS custom-subdomain CNAME target (docs-confirmed); s
- LEARN: REJECTED MISCONFIG @ www.onecode.de: static Webflow marketing, CF-cached HIT, no dynamic surface — no delta from runs 09-02..09-05
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: 95.130.17.37 no HTTP; non-web (mail) — out-of-scope class, no action
- LEARN: REJECTED MISCONFIG @ cto.onecode.de/hostmaster.*: Confidence 45 < 50; passive-only cannot confirm takeover without active DNS resolution

## RANKED HYPOTHESES 2026-09-06 17:44:25 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Two parallel unblocks (1) create a Perspective funnel account, attach custom subdomain cto.onecode.de (CNAME already → cname.perspective-dns.com), observ
- NEXT(hypotheses-nemotron3.txt): HUMAN: Escalate to obtain two invited test accounts for kurs.onecode.de to activate the post-auth BOLA hypothesis (conf 65, CRITICAL impact). Pre-auth surface e
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: re-confirmed 17:42 UTC — http 409 "error code:1001", CNAME → cname.perspective-dns.com (104.18.x) stable; hostname unbound/
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login HEAD 200, /api/broadcast 307 unchanged; pre-auth surface stable, no new cookie/session signal.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Probed again 2026-09-05 → 401 "Secret API key required" with publishable key; schema-cache down 
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1: Probed again → 503 (cache block, same as REST); no pre-auth introspection possible
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: Provider identified — cname.perspective-dns.com = Perspective funnel SaaS custom-subdomain CNAME target (docs-confirmed); s
- LEARN: REJECTED MISCONFIG @ www.onecode.de: static Webflow marketing, CF-cached HIT, no dynamic surface — no delta from runs 09-02..09-05
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: 95.130.17.37 no HTTP; non-web (mail) — out-of-scope class, no action
- LEARN: REJECTED MISCONFIG @ cto.onecode.de/hostmaster.*: Confidence 45 < 50; passive-only cannot confirm takeover without active DNS resolution

## RANKED HYPOTHESES 2026-09-06 20:17:37 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via missing Supabase RLS filter (from art/lead_bigpickle.txt)
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PASSIVE: Re-probe GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ with apikey header after 00:00Z 09-07 (cadence <=1/day). All other hypotheses blocked on
- NEXT(hypotheses-nemotron3.txt): HUMAN: Escalate to obtain two invited test accounts for kurs.onecode.de to activate the post-auth BOLA hypothesis (conf 65, CRITICAL impact). Pre-auth surface e
- LEARN: ACCEPTED MISCONFIG @ onecode.de: Live Webflow marketing (different page than www — "AI-native Entwickler" landing). Static, no dynamic surface — no new attack c
- LEARN: NO_DELTA @ kurs.onecode.de: 7 paths tested (/login, /passwort-vergessen, /api/broadcast, /api/health, /api/auth/session, /robots.txt, /sitemap.xml) — all unchan
- LEARN: NO_DELTA @ cto.onecode.de: 409 non-2xx persists; CNAME unbound/reclaimable; conf 58 stable.
- LEARN: NO_DELTA @ all: REST/recovery re-probe deferred to 09-07 per <=1/day cadence.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Probed again 2026-09-06 → 401 "Secret API key required" with publishable key; schema-cache down 
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1: Probed again → 503 (cache block, same as REST); no pre-auth introspection possible
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: Provider confirmed as Perspective funnel SaaS; stable TLS handshake failure + CNAME → cname.perspective-dns.com = hostname 
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution

## RANKED HYPOTHESES 2026-09-06 22:12:43 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via missing Supabase RLS filter (from art/lead_bigpickle.txt)
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PASSIVE: Re-probe GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ with apikey header after 00:00Z 09-07 (cadence <=1/day). All other hypotheses blocked on
- NEXT(hypotheses-nemotron3.txt): HUMAN: Escalate to obtain two invited test accounts for kurs.onecode.de to activate the post-auth BOLA hypothesis (conf 65, CRITICAL impact). Pre-auth surface e
- LEARN: NO_DELTA @ all: Fresh probes 22:11 UTC confirm identical state to 09-06 20:15 — kurs.onecode.de/login 200, cto 409/1001, storage empty, REST 401 anon-block.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires two invited test accounts.
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME → cname.perspective-dns.com stable 4+ days; 409/1001 + missing cert → hostname unbound/reclaimable; conf 58, HUMAN co
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint probeable, zero buckets — risk lowered but monitor active.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Explicit 401 anon-block with publishable key; monitor for cache recovery after 00:00Z 09-07.
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings).
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution.
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface.
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Probed again 2026-09-06 → 401 "Secret API key required" with publishable key; schema-cache down 
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1: Probed again → 503 (cache block, same as REST); no pre-auth introspection possible
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: Provider confirmed as Perspective funnel SaaS; stable TLS handshake failure + CNAME → cname.perspective-dns.com = hostname 
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution

## RANKED HYPOTHESES 2026-09-07 00:05:41 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via missing Supabase RLS filter (from art/lead_bigpickle.txt)
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PASSIVE: Re-probe GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ with apikey header after 00:00Z 09-08 (cadence <=1/day). All other hypotheses blocked on
- NEXT(hypotheses-nemotron3.txt): HUMAN: Escalate to obtain two invited test accounts for kurs.onecode.de to activate the post-auth BOLA hypothesis (conf 65, CRITICAL impact). Pre-auth surface e
- LEARN: NO_DELTA @ all: REST 401 anon-block persists; cto 409/1001 persists; storage empty; kurs.onecode.de/login 200 unchanged. Identical state to 09-06 22:11.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires two invited test accounts.
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME → cname.perspective-dns.com stable 5+ days; 409/1001 + missing cert → hostname unbound/reclaimable; conf 58, HUMAN co
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint probeable, zero buckets — risk lowered but monitor active.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Explicit 401 anon-block with publishable key; monitor for cache recovery after 00:00Z 09-08.
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings).
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution.
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface.
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Probed again 2026-09-06 → 401 "Secret API key required" with publishable key; schema-cache down 
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1: Probed again → 503 (cache block, same as REST); no pre-auth introspection possible
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: Provider confirmed as Perspective funnel SaaS; stable TLS handshake failure + CNAME → cname.perspective-dns.com = hostname 
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution

## RANKED HYPOTHESES 2026-09-07 04:57:10 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via missing Supabase RLS filter (from art/lead_bigpickle.txt)
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PASSIVE: Re-probe GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ with apikey header after 00:00Z 09-08 (cadence <=1/day). All other hypotheses blocked on
- NEXT(hypotheses-nemotron3.txt): HUMAN: Escalate to obtain two invited test accounts for kurs.onecode.de to activate the post-auth BOLA hypothesis (conf 65, CRITICAL impact). Pre-auth surface e
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: re-confirmed live 09-07 — GET http://cto.onecode.de/ = 409, HTTPS = empty/handshake-fail, CNAME → cname.perspective-dns.com
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: live re-probe 09-07 — HTTP 409/1001, HTTPS handshake-fail, CNAME → cname.perspective-dns.com stable; unbound/reclaimable; c
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login + /passwort-vergessen both 200 today; pre-auth surface stable, exhausted; no new cookie/session signal.
- LEARN: REJECTED MISCONFIG @ hostmaster.*/www/mail.onecode.de: unchanged classes — NXDOMAIN/static/non-web, no new surface.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Probed again 2026-09-06 → 401 "Secret API key required" with publishable key; schema-cache down 
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1: Probed again → 503 (cache block, same as REST); no pre-auth introspection possible
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: Provider confirmed as Perspective funnel SaaS; stable TLS handshake failure + CNAME → cname.perspective-dns.com = hostname 
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution

## RANKED HYPOTHESES 2026-09-07 10:03:58 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via missing Supabase RLS filter (from art/lead_bigpickle.txt)
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PASSIVE: Re-probe GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ with apikey header after 00:00Z 09-08 (cadence <=1/day). All other hypotheses blocked on
- NEXT(hypotheses-nemotron3.txt): HUMAN: Escalate to obtain two invited test accounts for kurs.onecode.de to activate the post-auth BOLA hypothesis (conf 65, CRITICAL impact). Pre-auth surface e
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: re-confirmed live 09-07 — GET http://cto.onecode.de/ = 409, HTTPS = empty/handshake-fail, CNAME → cname.perspective-dns.com
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login + /passwort-vergessen both 200 today; pre-auth surface stable, exhausted; no new cookie/session signal.
- LEARN: REJECTED MISCONFIG @ hostmaster.*/www/mail.onecode.de: unchanged classes — NXDOMAIN/static/non-web, no new surface.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Probed again 2026-09-06 → 401 "Secret API key required" with publishable key; schema-cache down 
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1: Probed again → 503 (cache block, same as REST); no pre-auth introspection possible
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: Provider confirmed as Perspective funnel SaaS; stable TLS handshake failure + CNAME → cname.perspective-dns.com = hostname 
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution

## RANKED HYPOTHESES 2026-09-07 15:58:33 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via missing Supabase RLS filter (from art/lead_bigpickle.txt)
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PASSIVE: Re-probe GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ with apikey header after 00:00Z 09-08 (cadence <=1/day). All other hypotheses blocked on
- NEXT(hypotheses-nemotron3.txt): HUMAN: Escalate to obtain two invited test accounts for kurs.onecode.de to activate the post-auth BOLA hypothesis (conf 65, CRITICAL impact). Pre-auth surface e
- LEARN: NO_DELTA @ all: REST 401 anon-block persists; cto 409/1001 persists; storage empty; kurs.onecode.de/login 200 unchanged. Identical state to 09-07 10:03.
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: re-confirmed live 15:55 UTC 09-07 — HTTP 409/1001, HTTPS handshake-fail, CNAME → cname.perspective-dns.com stable 5+ days; 
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal.
- LEARN: REJECTED MISCONFIG @ hostmaster.*/www/mail.onecode.de: unchanged classes — NXDOMAIN/static/non-web, no new surface.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Probed again 2026-09-06 → 401 "Secret API key required" with publishable key; schema-cache down 
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1: Probed again → 503 (cache block, same as REST); no pre-auth introspection possible
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: Provider confirmed as Perspective funnel SaaS; stable TLS handshake failure + CNAME → cname.perspective-dns.com = hostname 
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution

## RANKED HYPOTHESES 2026-09-07 19:53:53 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via missing Supabase RLS filter (from art/lead_bigpickle.txt)
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Escalate to obtain two invited test accounts for kurs.onecode.de to activate the post-auth BOLA hypothesis (conf 65, CRITICAL impact). Pre-auth surface f
- NEXT(hypotheses-nemotron3.txt): HUMAN: Escalate to obtain two invited test accounts for kurs.onecode.de to activate the post-auth BOLA hypothesis (conf 65, CRITICAL impact). Pre-auth surface e
- LEARN: NO_DELTA @ all: REST 401 anon-block persists (19:47 09-07); cto 409/CNAME→cname.perspective-dns.com persists; kurs /login+/passwort-vergessen 200 unchanged. Ide
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: re-confirmed live 19:47 UTC 09-07 — HTTP 409, CNAME→cname.perspective-dns.com stable 5+ days; hostname unbound/reclaimable;
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login + /passwort-vergessen 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal.
- LEARN: REJECTED MISCONFIG @ hostmaster.*/www/mail.onecode.de: unchanged classes — NXDOMAIN/static/non-web, no new surface.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Probed again 2026-09-06 → 401 "Secret API key required" with publishable key; schema-cache down 
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1: Probed again → 503 (cache block, same as REST); no pre-auth introspection possible
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: Provider confirmed as Perspective funnel SaaS; stable TLS handshake failure + CNAME → cname.perspective-dns.com = hostname 
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution

## RANKED HYPOTHESES 2026-09-07 22:42:59 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- [50] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Publishable-key REST exposure on schema-cache recovery (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: at first cycle after 00:00Z 09-08, GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit
- NEXT(hypotheses-nemotron3.txt): HUMAN: Escalate to obtain two invited test accounts for kurs.onecode.de to activate the post-auth BOLA hypothesis (conf 65, CRITICAL impact). Pre-auth surface e
- LEARN: NO_DELTA @ all: 22:40Z 09-07 — REST 401, cto 409/CNAME, storage empty, kurs /login+/passwort-vergessen 200, identical to 19:47Z run; all monitors at cadence lim
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME → cname.perspective-dns.com stable 5+ days; 409/1001 + missing cert = hostname unbound/reclaimable; conf 58, HUMAN co
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login + /passwort-vergessen 200 unchanged tonight; pre-auth surface stable and exhausted.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 401 anon-block persists; monitor for schema-cache recovery after 00:00Z 09-08.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME → cname.perspective-dns.com stable 5+ days; 409/1001 + missing cert → hostname unbound/reclaimable; conf 58, HUMAN co
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint probeable, zero buckets — risk lowered but monitor active
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Explicit 401 anon-block with publishable key; monitor for cache recovery after 00:00Z 2026-09-08
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login

## RANKED HYPOTHESES 2026-09-08 01:08:30 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME → cname.perspective-dns.com stable 6+ days; 409/1001 + missing cert → hostname unbound/reclaimable; conf 58, HUMAN co
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint probeable, zero buckets — risk lowered but monitor active
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Explicit 401 anon-block with publishable key; monitor for cache recovery after 00:00Z 2026-09-08
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login

## RANKED HYPOTHESES 2026-09-08 06:03:48 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- [50] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Publishable-key REST exposure on schema-cache recovery (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorizat
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 2026-09-08 probe (01:10Z) — the gateway FLIPPED from 401 anon-block back to 503 PGRST002 "Could not q
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME → cname.perspective-dns.com stable 6+ days; 409/1001 + missing cert → hostname unbound/reclaimable; conf 58, HUMAN co
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint probeable, zero buckets — risk lowered but monitor active
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Explicit 401 anon-block with publishable key; monitor for cache recovery after 00:00Z 2026-09-08
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login

## RANKED HYPOTHESES 2026-09-08 11:30:35 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- [50] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Publishable-key REST exposure on schema-cache recovery (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: <=1/day re-probe REST at next cycle. GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with publishable key — 503 PGRST002 p
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 2026-09-08 11:29Z probe — 503 PGRST002 persists (schema-cache-down mode). Gateway has now shown three
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: re-confirmed 11:29Z 09-08 — HTTP 409 "error code:1001", CNAME→cname.perspective-dns.com stable 6+ days; hostname unbound/re
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Empty bucket list confirmed — endpoint probeable but zero buckets exist.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME → cname.perspective-dns.com stable 6+ days; 409/1001 + missing cert → hostname unbound/reclaimable; conf 58, HUMAN co
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint probeable, zero buckets — risk lowered but monitor active
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Explicit 401 anon-block with publishable key; monitor for cache recovery after 00:00Z 2026-09-08
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login

## RANKED HYPOTHESES 2026-09-08 15:21:10 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PASSIVE: <=1/day REST re-probe at next cadence window (after 00:00Z 09-09). GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "a
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhausted
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 503 PGRST002 persists; gateway three-state oscillation confirmed (503→401→503); NOT permissive; 
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com live 15:20Z; 409/1001 + missing cert; hostname unbound/reclaimable; conf 58, HUMAN pending
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 unchanged; pre-auth surface stable, exhausted
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Empty bucket list — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404; no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401; requires auth
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME → cname.perspective-dns.com stable 6+ days; 409/1001 + missing cert → hostname unbound/reclaimable; conf 58, HUMAN co
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint probeable, zero buckets — risk lowered but monitor active
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Explicit 401 anon-block with publishable key; monitor for cache recovery after 00:00Z 2026-09-08
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME → cname.perspective-dns.com stable 6+ days; 409/1001 + missing cert → hostname unbound/reclaimable; conf 58, HUMAN co
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint probeable, zero buckets — risk lowered but monitor active
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Explicit 401 anon-block with publishable key; monitor for cache recovery after 00:00Z 2026-09-08
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login

## RANKED HYPOTHESES 2026-09-08 18:51:07 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PASSIVE: ≤1/day REST re-probe at next cadence window (after 00:00Z 09-09). GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with p
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires two invited test accounts; pre-auth fully exhau
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 503 PGRST002 persists (schema-cache-down mode); gateway three-state oscillation confirmed (503→4
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 6+ days; HTTP 409/1001 + HTTPS handshake-fail; hostname unbound/reclaimable; conf 58
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint probeable, zero buckets — risk lowered but monitor active.
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured.
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface.
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope.
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution.
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404; no deployed functions.
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401; requires auth.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 503 PGRST002 persists; gateway three-state oscillation confirmed (503→401→503); NOT permissive; 
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com live 15:20Z; 409/1001 + missing cert; hostname unbound/reclaimable; conf 58, HUMAN pending
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 unchanged; pre-auth surface stable, exhausted
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Empty bucket list — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404; no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401; requires auth

## RANKED HYPOTHESES 2026-09-08 21:47:30 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 4-state oscillation confirmed (503→401→503→401 since 09-04); NOT permissive on any obser
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com live 21:44Z; HTTP 409/1001 + TLS handshake-fail; hostname unbound/reclaimable; conf 58, HUM
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Empty bucket list — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404; no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401; requires auth

## RANKED HYPOTHESES 2026-09-08 23:58:20 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- [58] cto.onecode.de: Dangling Perspective CNAME subdomain takeover on cto.onecode.de (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: at 00:00Z 09-09 cadence window (last probe 23:57Z flipped to 503), GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with pu
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 23:57Z → 503 PGRST002 (flip from 21:44Z 401); 5-state oscillation 503→401→503→401→503 confirmed;
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: BOLA via RLS gap remains top (conf 65); 2 invited accounts required; pre-auth exhausted.
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 7 days; 409/1001 + no cert; conf 58, HUMAN confirm pending.
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 4-state oscillation confirmed (503→401→503→401 since 09-04); NOT permissive on any obser
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com live 21:44Z; HTTP 409/1001 + TLS handshake-fail; hostname unbound/reclaimable; conf 58, HUM
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Empty bucket list — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404; no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401; requires auth

## RANKED HYPOTHESES 2026-09-09 04:30:01 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 5-state oscillation confirmed (503→401→503→401→503 since 09-04); NOT permissive on any o
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 7+ days; 409/1001 + TLS handshake-fail; hostname unbound/reclaimable; conf 58, HUMAN
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Empty bucket list — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404; no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401; requires auth

## RANKED HYPOTHESES 2026-09-09 09:12:24 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: at 00:00Z 09-10 cadence window, GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with publishable key (apikey + Bearer) — i
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: BOLA via RLS gap remains top (conf 65); 2 invited accounts required; pre-auth exhausted.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 6-state oscillation confirmed (503→401→503→401→503→503 since 09-04); NOT permissive on a
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 7+ days; 409/1001 + no cert; conf 58, HUMAN confirm pending.
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 5-state oscillation confirmed (503→401→503→401→503 since 09-04); NOT permissive on any o
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 7+ days; 409/1001 + TLS handshake-fail; hostname unbound/reclaimable; conf 58, HUMAN
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Empty bucket list — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404; no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401; requires auth

## RANKED HYPOTHESES 2026-09-09 13:52:43 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: at 00:00Z 09-10 cadence window, GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with publishable key (apikey + Bearer) — i
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 6-state oscillation confirmed (503→401→503→401→503→503 since 09-04); NOT permissive on a
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 7+ days; 409/1001 + no cert; conf 58, HUMAN confirm pending.
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 5-state oscillation confirmed (503→401→503→401→503 since 09-04); NOT permissive on any o
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 7+ days; 409/1001 + TLS handshake-fail; hostname unbound/reclaimable; conf 58, HUMAN
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Empty bucket list — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured
- LEARN: REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface
- LEARN: REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope
- LEARN: REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404; no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401; requires auth

## RANKED HYPOTHESES 2026-09-09 17:44:36 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: at 00:00Z 09-10 cadence window, GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with publishable key (apikey + Bearer) — i
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 6-state oscillation confirmed (503→401→503→401→503→503 since 09-04); NOT permissive on a
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 7+ days; 409/1001 + no cert; conf 58, HUMAN confirm pending.
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 6-state oscillation confirmed (503→401→503→401→503→503 since 09-04); NOT permissive on a
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 7+ days; 409/1001 + no cert; conf 58, HUMAN confirm pending
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible

## RANKED HYPOTHESES 2026-09-09 20:49:39 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: at 00:00Z 09-10 cadence window, GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with publishable key (apikey + Bearer) — i
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 6-state oscillation confirmed (503→401→503→401→503→503 since 09-04); NOT permissive on a
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 7+ days; 409/1001 + no cert; conf 58, HUMAN confirm pending.
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible.
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 20:47Z 09-09 probe → 503 PGRST002; 7-state oscillation confirmed (503→401→503→401→503→401→503 si
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: re-confirm 20:47Z 09-09 — 409/1001, CNAME→cname.perspective-dns.com stable 7+ days; unbound/reclaimable; conf 58, HUMAN pen
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 7-state oscillation confirmed (503→401→503→401→503→503→401 since 09-04); NOT permissive 
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 7+ days; 409/1001 + no cert; conf 58, HUMAN confirm pending
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible

## RANKED HYPOTHESES 2026-09-09 23:16:20 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: at 00:00Z 09-10 cadence window, GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with publishable key (apikey + Bearer) — i
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 23:06Z 09-09 probe → 503 PGRST002 (flip from 401); 8-state oscillation 503→401→503→401→503→503→4
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: re-confirm 23:06Z 09-09 — 409/1001, CNAME→cname.perspective-dns.com stable 8 days; unbound/reclaimable; conf 58, HUMAN pend
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login + /passwort-vergessen 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible

## RANKED HYPOTHESES 2026-09-10 01:13:07 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: at next cadence window (post 00:00Z 09-11), GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with publishable key (apikey +
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 00:10Z 09-10 probe → 503 PGRST002 (no flip; 9th seq observation, 8-state oscillation 503→401→503
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: re-confirm 00:10Z 09-10 — 409/1001 + TLS handshake-fail, CNAME→cname.perspective-dns.com stable 8+ days; unbound/reclaimabl
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login + /passwort-vergessen 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 9-state oscillation confirmed (503→401→503→401→503→503→401→503→401 since 09-04); NOT per
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 8+ days; 409/1001 + no cert; conf 58, HUMAN confirm pending
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible

## RANKED HYPOTHESES 2026-09-10 06:10:05 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: at next cadence window (post 00:00Z 09-11), GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with sb_publishable key (apike
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 06:08Z 09-10 probe → 503 PGRST002 with sb_publishable key (10th sequential observation; oscillat
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: re-confirm 06:08Z 09-10 — 409/1001 + TLS handshake-fail, CNAME→cname.perspective-dns.com stable 9+ days; unbound/reclaimabl
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login + /passwort-vergessen 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 10-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401 since 09-04); NO
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 8+ days; 409/1001 + no cert; conf 58, HUMAN confirm pending
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible

## RANKED HYPOTHESES 2026-09-10 11:33:14 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: at next cadence window (post 00:00Z 09-11), GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with sb_publishable key (apike
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 10-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401 since 09-04); NO
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 8+ days; 409/1001 + no cert; conf 58, HUMAN confirm pending
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 10-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401 since 09-04); NO
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 8+ days; 409/1001 + no cert; conf 58, HUMAN confirm pending
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-10 15:13:38 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: at next cadence window (post 00:00Z 09-11), GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with sb_publishable key (apike
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: NO_DELTA @ all: REST 503 PGRST002 persists (11:34Z 09-10); cto 409/CNAME stable; kurs /login 200 unchanged. Identical to 06:08Z.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 11th sequential 503 PGRST002 observation; 11-state oscillation confirmed (503→401→503→401→503→50
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 9+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm 
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 10-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401 since 09-04); NO
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 8+ days; 409/1001 + no cert; conf 58, HUMAN confirm pending
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-10 18:36:05 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: at next cadence window (post 00:00Z 09-11), GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with sb_publishable key (apike
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 11th sequential 503 PGRST002 observation; 11-state oscillation confirmed (503→401→503→401→503→50
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 9+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm 
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 11-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503 since 09-04)
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 9+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm 
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-10 21:16:03 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: at next cadence window (post 00:00Z 09-11), GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with headers apikey + Authoriz
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical (200/307, r
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable (dig 21:13Z 09-10); no domain-verification TXT present; conf 58, HUMAN claim-attempt
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307 re-confirmed 21:14Z; no new cookie/session signal; pre-auth surface stays exhausted.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: cadence-held this cycle (last 11:34Z 09-10 = 503, 11th sequential); REST gateway monitor stays active
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 11-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503 since 09-04)
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 9+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm 
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-10 23:16:33 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: at next cadence window (post 00:00Z 09-11), GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with headers apikey + Authoriz
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: live dig 23:15Z 09-10 — CNAME→cname.perspective-dns.com stable 9+ days; no TXT verification record; conf 58, HUMAN claim-at
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: HEAD /login 200 (no-store) + / 307 re-confirmed 23:15Z; x-railway-edge lax1 (iad1→lax1 region shift after migration); no new co
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 12th-probe cadence-held this cycle (last 11:34Z 09-10 = 503, 11th sequential); monitor re-arms post 0
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 11-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503 since 09-04)
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 9+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm 
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-11 01:16:51 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 11-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503 since 09-04)
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 9+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm 
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-11 06:11:04 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorizat
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 11-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503 since 09-04)
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 9+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm 
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible.
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 12-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401 since 09
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 10+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-11 11:33:54 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorizat
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 13th probe = 401 anon-block (flip from 503); 12-state oscillation persists (503→401→503→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 10+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: CHANGED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint shifted from 200 `[]` to 400; possible Supabase project config change; monitor for fu
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 12-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401 since 09
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 10+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/storage(empty): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-11 15:15:09 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with sb_publishable key — next cadence window post 00:00Z 09-12. Parallel 
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_p
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 14th probe = 503 PGRST002 (flip from 401 at 06:11Z); 13-state oscillation persists (503→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 10+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: CHANGED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 400 blip at 11:33Z reverted to 200 `[]` with publishable key; transient, not config change.
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 12-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401 since 09
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 10+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: CHANGED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint shifted from 200 `[]` to 400; possible Supabase project config change; monitor for fu
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-11 18:41:26 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 13-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503 
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 10+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-11 21:22:04 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with headers `apikey`+`Authorization` = `sb_publishable_g48Bd8qEtLesgk0zgz
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED AUTH @ aygnpacdkgtsfnhgcyjc.supabase.co/auth/v1/settings: re-validated 09-11 — all external providers false (email-only, signup disabled, passkeys off)
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: HEAD /login 200; CNAME→ki8dqcf6.up.railway.app stable post-migration.
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: dig 09-11 — CNAME→cname.perspective-dns.com stable 10+ days; 409/1001 + TLS-fail; unbound/reclaimable; conf 58, HUMAN pendi
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 13-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503 
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 10+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-11 23:34:01 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with headers `apikey`+`Authorization` = `sb_publishable_g48Bd8qEtLesgk0zgz
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: BOLA via RLS gap still top (conf 65); two invited accounts gating; pre-auth exhausted; no delta 09-11.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 23:31Z same-day HEAD confirms state held; 14th obs = 503; 13-state oscillation persists; never p
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com + HTTP 409 re-confirmed 23:31Z; stable 10+ days; conf 58, HUMAN claim-attempt only proof pa
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure; unchanged.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 13-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503 
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 10+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-12 01:35:28 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with headers `apikey`+`Authorization` = `sb_publishable_g48Bd8qEtLesgk0zgz
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 13-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503 
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 10+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-12 06:34:15 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with headers `apikey`+`Authorization` = `sb_publishable_g48Bd8qEtLesgk0zgz
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed 06:30Z 09-12; pre-auth surface stable, exhausted; no new cookie/session signal.
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 06:30Z dig — CNAME→cname.perspective-dns.com stable 11+ days, explicit TXT = zero records, HTTP 409/HTTPS handshake-fail; c
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` baseline holds (post-400-blip); endpoint probeable, zero buckets.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: cadence-held this cycle (last 01:33Z 09-12 = 503, 15th sequential); REST monitor arms post-00:00Z 09-
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure; unchanged 09-12.

## RANKED HYPOTHESES 2026-09-12 11:17:19 UTC
- [58] cto.onecode.de: Dangling Perspective CNAME takeover on cto.onecode.de (from art/lead_bigpickle.txt)
- [45] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Supabase REST gateway schema-cache recovery exposing anon table access (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with headers `apikey`+`Authorization` = `sb_publishable_g48Bd8qEtLesgk0zgz
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed 06:30Z 09-12; pre-auth surface stable, exhausted; no new cookie/session signal.
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 06:30Z dig — CNAME→cname.perspective-dns.com stable 11+ days, explicit TXT = zero records, HTTP 409/HTTPS handshake-fail; c
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` baseline holds (post-400-blip); endpoint probeable, zero buckets.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: cadence-held this cycle (last 01:33Z 09-12 = 503, 15th sequential); REST monitor arms post-00:00Z 09-
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure; unchanged 09-12.
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed 11:16Z 09-12 (x-railway-edge lax1, x-hikari-trace lax1.ez9k); pre-auth surface stable, e
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 11:16Z dig — CNAME→cname.perspective-dns.com stable day 12 (104.18.2.73/104.18.3.73), IP-resolved TXT zero records, HTTP 40
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` re-confirmed 11:16Z 09-12; endpoint probeable, zero buckets.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: cadence-held this cycle (last 01:33Z 09-12 = 503, 15th sequential); 16th probe arms post-00:00Z 09-13
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure; unchanged 09-12.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 14-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 11+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-12 14:17:40 UTC
- [50] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Publishable-key REST exposure on schema-cache recovery (from art/lead_bigpickle.txt)
- [45] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Supabase REST gateway schema-cache recovery exposing anon table access (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with headers `apikey`+`Authorization`=`sb_publishable_g48Bd8qEtLesgk0zgzTR
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 14:15Z dig — CNAME→cname.perspective-dns.com stable day 12, HTTP 409, no TXT; conf 58, HUMAN claim-attempt only proof path.
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login HEAD 200 re-confirmed 14:15Z 09-12; pre-auth surface stable, exhausted; no new cookie/session signal.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: cadence-held (last 01:33Z 09-12 = 503, 15th seq); 16th probe arms post-00:00Z 09-13.
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires 2 invited test accounts; pre-auth fully exhaust
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 14-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 12+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-12 17:25:46 UTC
- [50] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Publishable-key REST exposure on schema-cache recovery (from art/lead_bigpickle.txt)
- [45] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Supabase REST gateway schema-cache recovery exposing anon table access (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with headers `apikey`+`Authorization`=`sb_publishable_g48Bd8qEtLesgk0zgzTR
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 503 PGRST002 persists on 16th probe (09-12); gateway oscillation continues; NOT permissive on any obs
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` baseline holds — endpoint probeable, zero buckets.
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 unchanged; pre-auth surface stable, exhausted.
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 12+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 15-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 12+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed 14:15Z 09-12; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-12 19:30:39 UTC
- [50] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Publishable-key REST exposure on schema-cache recovery (from art/lead_bigpickle.txt)
- [45] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Supabase REST gateway schema-cache recovery exposing anon table access (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed 19:29Z 09-12 (railway-hikari, x-railway-edge lax1, x-hikari-trace lax1.ez9k); pre-auth s
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 19:29Z dig — CNAME→cname.perspective-dns.com stable day 12 (A 104.18.2.73/104.18.3.73), TXT zero, HTTP 409 live; conf 58, H
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` re-confirmed 19:29Z 09-12 — endpoint probeable, zero buckets.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: cadence-held (no probe today; last = 401 at 17:25Z 09-12, 16th obs); 17th probe arms post-00:00Z 09-1
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 15-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 12+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed 14:15Z 09-12; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-12 21:41:03 UTC
- [50] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Publishable-key REST exposure on schema-cache recovery (from art/lead_bigpickle.txt)
- [45] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Supabase REST gateway schema-cache recovery exposing anon table access (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: 00:00Z 09-13 → GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30"
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + no Set-Cookie re-confirmed 21:38Z 09-12 (railway-hikari, x-railway-edge lax1); pre-auth surface stable, exhausted.
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 21:38Z dig — CNAME→cname.perspective-dns.com stable day 12 (104.18.2.73/104.18.3.73), TXT zero, HTTP 409 live; conf 58, HUM
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: cadence-held this cycle (last = 401 at 17:25Z 09-12, 16th obs); 17th probe arms post-00:00Z 09-13.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 15-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 12+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed 14:15Z 09-12; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-12 23:25:05 UTC
- [50] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Publishable-key REST exposure on schema-cache recovery (from art/lead_bigpickle.txt)
- [45] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Supabase REST gateway schema-cache recovery exposing anon table access (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: 00:00Z 09-13 → GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30"
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login + no Set-Cookie re-probed 23:24Z 09-12 (railway-hikari, x-railway-edge iad1 — lax1→iad1 region flip, 
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 23:24Z — CNAME→cname.perspective-dns.com day-12, authoritative TXT = zero records (SOA only), HTTP 409; conf 58, HUMAN clai
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` re-confirmed 23:24Z 09-12 — endpoint probeable, zero buckets.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: cadence-held (last = 401 @ 17:25Z 09-12, 16th obs); 17th probe arms post-00:00Z 09-13.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 15-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 12+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed 14:15Z 09-12; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-13 01:26:11 UTC
- [45] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Supabase REST gateway schema-cache recovery exposing anon table access (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 17th probe 00:24Z 09-13 → 503 PGRST002 (flip from 401); 16-state oscillation (…→401→503) since 0
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 01:24Z — CNAME→cname.perspective-dns.com day-13, zero verification TXT, HTTP 409 live; conf 58, HUMAN claim-attempt only pr
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + no Set-Cookie + no-store re-confirmed 01:24Z 09-13 (railway-hikari, x-railway-edge iad1, x-hikari-trace iad1.trg5)
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 15-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 12+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed 14:15Z 09-12; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-13 06:48:36 UTC
- [58] cto.onecode.de: Dangling Perspective CNAME takeover on cto.onecode.de (from art/lead_bigpickle.txt)
- [45] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Supabase REST gateway schema-cache recovery exposing anon table access (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 09-14 → GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: HEAD /login 200 (x-railway-edge lax1, x-hikari-trace lax1.sx7j, no Set-Cookie, private/no-store) re-confirmed 06:46Z 09-13; pre
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: dig 06:46Z 09-13 — CNAME→cname.perspective-dns.com day-13 (A 104.18.2.73/3.73), TXT zero, HTTP 409 live, HTTPS handshake-fa
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` re-confirmed 06:46Z 09-13 — endpoint probeable, zero buckets.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: cadence-held (17th probe 00:24Z 09-13 = 503, 16-state oscillation); 18th probe arms post-00:00Z 09-14
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 16-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 13+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-13 12:43:31 UTC
- [45] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Supabase REST gateway schema-cache recovery exposing anon table access (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 16-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 13+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-13 16:42:35 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_bigpickle.txt)
- [45] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Supabase REST gateway schema-cache recovery exposing anon table access (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 2026-09-14 (18th probe, ≤1/day cadence): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publis
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 16-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 13+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-13 19:05:29 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_bigpickle.txt)
- [45] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Supabase REST gateway schema-cache recovery exposing anon table access (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 2026-09-14 (18th probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: dig 19:00Z 09-13 — CNAME→cname.perspective-dns.com day-13 (A 104.18.2.73/3.73), TXT zero, HTTP 409; conf 58, HUMAN claim-at
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 (railway-hikari, lax1.sx7j, no Set-Cookie) + / 307→/login re-confirmed 19:00Z 09-13; pre-auth surface stable, exhaus
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` re-confirmed 19:00Z 09-13 — endpoint probeable, zero buckets.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: cadence-held (17th probe 00:24Z 09-13 = 503); 18th probe arms post-00:00Z 09-14.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 16-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 13+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-13 21:26:55 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 2026-09-14 (18th, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g48Bd8qE
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 16-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 13+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-13 23:38:27 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- [50] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Publishable-key REST table exposure on schema-cache recovery (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 2026-09-14 (18th, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g48Bd8qE
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: live 21:28Z 09-13 — CNAME→cname.perspective-dns.com day-13 (104.18.2.73/3.73), authoritative TXT zero, HTTP 409; conf 58, H
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 (railway-hikari) + / 307→/login re-confirmed 21:28Z 09-13; pre-auth surface stable, exhausted.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: cadence-held (17th probe 00:24Z 09-13 = 503, 16-state oscillation); 18th probe arms post-00:00Z 09-14
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 17-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 13+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-14 01:53:33 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- [50] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Publishable-key REST table exposure on schema-cache recovery (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 2026-09-15 (19th, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g48Bd8qE
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 17-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 13+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 17-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 13+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 17-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 13+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-14 07:11:55 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 2026-09-15 (19th, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g48Bd8qE
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 18th probe 01:42Z 09-14 = 503 PGRST002 (no flip); 17-state oscillation persists (…→401→503 since 09-0
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 14+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login stable; pre-auth surface exhausted; no new cookie/session signal.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets.
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 17-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 13+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-14 14:23:38 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 2026-09-15 (20th probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 19th probe 14:16Z 09-14 = 503 PGRST002 (no flip); 18-state oscillation persists; never permissive; mo
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 409/1001 live 14:16Z 09-14; CNAME→cname.perspective-dns.com stable 14+ days; conf 58, HUMAN pending.
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 unchanged; pre-auth surface stable, exhausted.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets.
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 17-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 13+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login re-confirmed; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: Railway CNAME target migrated tgk4io5m→ki8dqcf6.up.railway.app (verified 21:14Z 09-10); app behavior identical; railway.ap
- LEARN: REJECTED MISCONFIG @ *.onecode.de (subdomain discovery): no new CT-observable subdomains beyond the 5 known hosts; inventory confirmed complete

## RANKED HYPOTHESES 2026-09-14 19:33:50 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 2026-09-15 (20th probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishabl
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login + no Set-Cookie re-confirmed 14:16Z 09-14 (railway-hikari, x-railway-edge lax1); pre-auth surface sta
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: TLS handshake-fail + CNAME→cname.perspective-dns.com (A 104.18.2.73/3.73) re-confirmed; stable 14+ days; conf 58, HUMAN cla
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 19th probe 14:16Z 09-14 = 503 PGRST002 (no flip); 18-state oscillation persists; never permissive; mo
- LEARN: Supabase platform enforces `sb_publishable_` key format only; legacy JWT anon keys (`eyJhbGci...`) rejected globally as "Invalid API key" — confirmed platform-l
- LEARN: Certspotter CT scan 21:14Z 09-10: exactly 5 names (`onecode.de`, `www`, `kurs`, `cto`, `mta-sts`) — inventory complete, zero new subdomains
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 19th probe 14:16Z 09-14 = 503 PGRST002 (no flip); 18-state oscillation persists; never permissive; mo
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 409/1001 live 14:16Z 09-14; CNAME→cname.perspective-dns.com stable 14+ days; conf 58, HUMAN pending
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 17-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-14 22:56:04 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: after 00:00Z 2026-09-15 (20th probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g
- NEXT(hypotheses-nemotron3.txt): PROBE: post-00:00Z 2026-09-15 (21st probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + no Set-Cookie re-confirmed 22:45Z 09-14 (railway-hikari, x-railway-edge iad1 region-flip noise); pre-auth surface 
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 22:45Z dig — CNAME→cname.perspective-dns.com day-14 (A 104.18.2.73/3.73), TXT zero, HTTP 409 implicit; conf 58, HUMAN claim
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 re-confirmed 22:45Z 09-14 — endpoint probeable, zero buckets.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: cadence-held (last probe 14:16Z 09-14 = 503, 19th obs); 20th probe arms post-00:00Z 09-15.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 20th probe 22:47Z 09-14 = 401 (flip from 503 at 14:16Z); 19-state oscillation persists; never pe
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 409/1001 live 22:47Z 09-14; CNAME→cname.perspective-dns.com stable 14+ days; conf 58, HUMAN pending
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/graphql(503): no pre-auth exposure possible
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 19-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-15 01:19:45 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: post-00:00Z 2026-09-15 (21st probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 20th probe 22:47Z 09-14 = 401 (flip from 503 at 14:16Z); 19-state oscillation persists; never pe
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 409/1001 live 22:47Z 09-14; CNAME→cname.perspective-dns.com stable 14+ days; conf 58, HUMAN pending
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/graphql(503): no pre-auth exposure possible
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 19-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-15 06:15:55 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 2026-09-16 (22nd probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- NEXT(hypotheses-nemotron3.txt): PROBE: post-00:00Z 2026-09-15 (21st probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 21st probe 06:14Z 09-15 = 503 PGRST002 (flip from 401); 20-state oscillation persists (…→401→503 sinc
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged 06:14Z 09-15 (railway-hikari, x-railway-edge lax1); pre-auth surface stable, exhausted; no 
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 15+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets.
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 20th probe 22:47Z 09-14 = 401 (flip from 503 at 14:16Z); 19-state oscillation persists; never pe
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 409/1001 live 22:47Z 09-14; CNAME→cname.perspective-dns.com stable 14+ days; conf 58, HUMAN pending
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401)/graphql(503): no pre-auth exposure possible
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 19-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-15 11:57:38 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 2026-09-16 (23rd probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- NEXT(hypotheses-nemotron3.txt): PROBE: post-00:00Z 2026-09-16 (22nd probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 22nd probe 01:17Z 09-15 = 503 PGRST002 (flip from 401); 21-state oscillation persists (…→401→503 sinc
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged 11:55Z 09-15; pre-auth surface stable, exhausted; no new cookie/session signal.
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 15+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets.
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 21st probe 06:14Z 09-15 = 503 PGRST002 (flip from 401); 20-state oscillation persists; never per
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 15+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged 06:14Z 09-15; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 19-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-15 16:53:45 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 2026-09-17 (24th probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- NEXT(hypotheses-nemotron3.txt): PROBE: post-00:00Z 2026-09-16 (22nd probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 23rd probe 01:16Z 09-16 = 503 PGRST002 (no flip); 22-state oscillation persists; never permissive; mo
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged 09-16; pre-auth surface stable, exhausted; no new cookie/session signal.
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 16+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets.
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 21st probe 06:14Z 09-15 = 503 PGRST002 (flip from 401); 20-state oscillation persists; never per
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 15+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged 06:14Z/11:55Z 09-15; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 20-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-15 19:57:14 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 2026-09-17 (24th probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- NEXT(hypotheses-nemotron3.txt): PROBE: post-00:00Z 2026-09-17 (24th probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged 09-15; pre-auth surface stable, exhausted; no new cookie/session signal.
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 17+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: cadence-held this cycle (last = 503 @ 01:16Z 09-16, 23rd obs); 24th probe arms post-00:00Z 09-17.
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 23rd probe 01:16Z 09-16 = 503 PGRST002 (no flip); 22-state oscillation persists; never permissiv
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 16+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged 09-16; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 22-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-15 22:55:53 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 2026-09-17 (24th probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- NEXT(hypotheses-nemotron3.txt): PROBE: post-00:00Z 2026-09-17 (24th probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + no Set-Cookie + railway-hikari (iad1) re-confirmed 22:48Z 09-15; pre-auth surface stable, exhausted.
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 15+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` re-confirmed 22:48Z 09-15 — endpoint probeable, zero buckets.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: cadence-held this cycle (last = 503 @ 01:16Z 09-16, 23rd obs); 24th probe arms post-00:00Z 09-17.
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 23rd probe 01:16Z 09-16 = 503 PGRST002 (no flip); 22-state oscillation persists; never permissiv
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 16+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged 09-16; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 22-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-16 01:13:36 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_bigpickle.txt)
- [45] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Supabase REST gateway schema-cache recovery exposing anon table access (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 2026-09-17 (24th probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- NEXT(hypotheses-nemotron3.txt): PROBE: post-00:00Z 2026-09-17 (24th probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login HEAD 200 + no Set-Cookie re-confirmed 01:11Z 09-16 (railway-hikari, x-railway-edge iad1); pre-auth surface stable, exhau
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: dig 09-16 — CNAME→cname.perspective-dns.com day-17 (104.18.2.73/3.73), zero verification TXT; HTTP 409 implicit; conf 58, H
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` re-confirmed 01:11Z 09-16 — endpoint probeable, zero buckets.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: cadence-held this cycle (last = 503 @ 01:16Z 09-16, 23rd obs); 24th probe arms post-00:00Z 09-17.
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 23rd probe 01:16Z 09-16 = 503 PGRST002 (no flip); 22-state oscillation persists; never permissiv
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 16+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged 09-16; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 22-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-16 06:13:42 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_bigpickle.txt)
- [45] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Supabase REST gateway schema-cache recovery exposing anon table access (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 2026-09-17 (24th probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- NEXT(hypotheses-nemotron3.txt): PROBE: post-00:00Z 2026-09-17 (24th probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login HEAD 200 + no Set-Cookie re-confirmed 01:11Z 09-16 (railway-hikari, x-railway-edge iad1); pre-auth surface stable, exhau
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: dig 09-16 — CNAME→cname.perspective-dns.com day-17 (104.18.2.73/3.73), zero verification TXT; HTTP 409 implicit; conf 58, H
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` re-confirmed 01:11Z 09-16 — endpoint probeable, zero buckets.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: cadence-held this cycle (last = 503 @ 01:16Z 09-16, 23rd obs); 24th probe arms post-00:00Z 09-17.
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 23rd probe 01:16Z 09-16 = 503 PGRST002 (no flip); 22-state oscillation persists; never permissiv
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 16+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged 09-16; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 22-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-16 11:51:46 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_bigpickle.txt)
- [45] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Supabase REST gateway schema-cache recovery exposing anon table access (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 2026-09-17 (24th probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- NEXT(hypotheses-nemotron3.txt): PROBE: post-00:00Z 2026-09-17 (24th probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login HEAD 200 + no Set-Cookie re-confirmed 01:11Z 09-16 (railway-hikari, x-railway-edge iad1); pre-auth surface stable, exhau
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: dig 09-16 — CNAME→cname.perspective-dns.com day-17 (104.18.2.73/3.73), zero verification TXT; HTTP 409 implicit; conf 58, H
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` re-confirmed 01:11Z 09-16 — endpoint probeable, zero buckets.
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: cadence-held this cycle (last = 503 @ 01:16Z 09-16, 23rd obs); 24th probe arms post-00:00Z 09-17.
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects.
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 23rd probe 01:16Z 09-16 = 503 PGRST002 (no flip); 22-state oscillation persists; never permissiv
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 16+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged 09-16; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 22-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-16 16:35:51 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 2026-09-17 (final closeout, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishabl
- NEXT(hypotheses-nemotron3.txt): PROBE: post-00:00Z 2026-09-17 (24th probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: supplementary 24th obs 16:33Z 09-16 = 503 PGRST002 (no flip) on /profiles + /enrollments; confid
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: HEAD /login 200 + no Set-Cookie re-confirmed 16:34Z 09-16 (railway-hikari, x-railway-edge lax1); /api/v1/health, /v1/health, /a
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: dig 16:34Z 09-16 — CNAME→cname.perspective-dns.com day-17 (104.18.2.73/3.73), zero verification TXT; HTTP 409; conf 58, HUM
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` re-confirmed 16:34Z 09-16 — endpoint probeable, zero buckets.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 23rd probe 01:16Z 09-16 = 503 PGRST002 (no flip); 22-state oscillation persists; never permissiv
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 16+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged 09-16; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 22-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-16 20:03:42 UTC

## RANKED HYPOTHESES 2026-09-16 22:48:57 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 2026-09-17 (final closeout, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishabl
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth.
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: dig 09-16 — CNAME→cname.perspective-dns.com day-17, TXT zero, SOA present; 409/1001; conf 58, HUMAN claim-attempt only proo
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + no Set-Cookie stable; pre-auth surface now exhaustively re-validated including two newly excluded vectors.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — zero buckets.

## RANKED HYPOTHESES 2026-09-17 01:14:53 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok

## RANKED HYPOTHESES 2026-09-17 06:18:37 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: post-00:00Z 2026-09-17 (final closeout, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishabl
- NEXT(hypotheses-nemotron3.txt): PROBE: post-00:00Z 2026-09-17 (24th probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g4
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth.
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: dig 09-16 — CNAME→cname.perspective-dns.com day-17, TXT zero, SOA present; 409/1001; conf 58, HUMAN claim-attempt only proo
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + no Set-Cookie stable; pre-auth surface now exhaustively re-validated including two newly excluded vectors.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — zero buckets.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 23rd probe 01:16Z 09-16 = 503 PGRST002 (no flip); 22-state oscillation persists; never permissiv
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 17+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged 09-16; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED MISCONFIG @ functions(404)/realtime(401): no pre-auth exposure possible
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Gateway 22-state oscillation confirmed (503→401→503→401→503→503→401→503→401→401→503→401→401→503→
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth

## RANKED HYPOTHESES 2026-09-17 11:54:25 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: post-00:00Z 2026-09-18 (cadence probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 503 PGRST002 persists; 22+ state oscillation (503↔401) since 09-04; never permissive; monitor st
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 17+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-17 16:42:11 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- NEXT(hypotheses-nemotron3.txt): PROBE: post-00:00Z 2026-09-18 (cadence probe, ≤1/day): GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: BOLA via RLS gap remains the sole actionable lead (conf 65); pre-auth surface exhausted 18 days, zero permissive obs
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com day-18, TXT zero; unbound/reclaimable; conf 58 holds; HUMAN claim-attempt is the only proof
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection i
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 503 PGRST002 persists; 22+ state oscillation (503↔401) since 09-04; never permissive; monitor st
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 17+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-17 19:53:26 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection i
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 18+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-17 22:45:48 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- LEARN: ACCEPTED IDOR(post-auth) @ kurs.onecode.de: BOLA via RLS gap sole actionable lead (conf 65); pre-auth surface exhausted 18.5 days, zero permissive observations;
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com day-19, TXT zero (fresh dig 09-17); unbound/reclaimable; conf 58 holds; HUMAN claim-attempt
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection platform-e
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection i
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 18+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-18 01:09:29 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 18+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-18 06:08:40 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: 06:04Z 09-18 re-probe — /login 200, / 307, /api/broadcast 307, x-middleware-subrequest still non-bypassing; pre-auth surface un
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 06:04Z 09-18 — CNAME→cname.perspective-dns.com day-20 (104.18.2.73/3.73), HTTP 409 live, TXT zero; conf 58 holds; HUMAN cla
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds 06:04Z 09-18 — endpoint probeable, zero buckets; unchanged.
- LEARN: REJECTED MISCONFIG @ all sources: triage 7Q gate returned empty twice (01:06Z/06:01Z 09-18) — no new findings to validate; confirms all pre-auth & REST monitors
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 18+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-18 11:31:12 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 20+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-18 15:11:32 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: new build live 15:09Z 09-18 — chunk 0-mbmp1iqb6hj.js, route refs {/admin,/courses,/dashboard,/einladung,/passwort-neu,/pas
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 15:09Z 09-18 dig — CNAME→cname.perspective-dns.com day-21, TXT zero (no verification record), A 104.18.2.73/3.73; conf 58 h
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds 15:09Z 09-18 — endpoint probeable, zero buckets; unchanged.
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 20+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-18 18:41:09 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: 18:34Z 09-18 — /login 200 (no Set-Cookie, private/no-store, railway-hikari lax1.v9kt); RSC route literals only /passwort-verges
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 18:34Z dig — CNAME→cname.perspective-dns.com day-21, pure CNAME (TXT not reachable at host); kurs CNAME ki8dqcf6 stable; co
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 18:34Z — 401 anon-block flip from 503 (expected 503↔401 oscillation since 09-04); never 200+rows; clo
- LEARN: REJECTED MISCONFIG @ kurs.onecode.de: sourcemaps 404 on all chunks; no buildId dir; /_next/static 308 — no recon/disclosure value from build artifacts.
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: new build live 15:09Z 09-18 — chunk 0-mbmp1iqb6hj.js, route refs {/admin,/courses,/dashboard,/einladung,/passwort-neu,/pas
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 20+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-18 21:16:49 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: new build live 15:09Z 09-18 — chunk 0-mbmp1iqb6hj.js, route refs {/admin,/courses,/dashboard,/einladung,/passwort-neu,/pas
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 15:09Z 09-18 dig — CNAME→cname.perspective-dns.com day-21, TXT zero (no verification record), A 104.18.2.73/3.73; conf 58 h
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds 15:09Z 09-18 — endpoint probeable, zero buckets; unchanged.
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: 18:34Z 09-18 — /login 200 (no Set-Cookie, private/no-store, railway-hikari lax1.v9kt); RSC route literals only /passwort-verges
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 18:34Z dig — CNAME→cname.perspective-dns.com day-21, pure CNAME (TXT not reachable at host); kurs CNAME ki8dqcf6 stable; co
- LEARN: ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 18:34Z — 401 anon-block flip from 503 (expected 503↔401 oscillation since 09-04); never 200+rows; clo
- LEARN: REJECTED MISCONFIG @ kurs.onecode.de: sourcemaps 404 on all chunks; no buildId dir; /_next/static 308 — no recon/disclosure value from build artifacts.
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: 21:15Z 09-18 — chunk 0-mbmp1iqb6hj.js sha256 f916f314... unchanged since 15:09Z build; /login 200 serving co-resident old 
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 21:15Z dig — CNAME→cname.perspective-dns.com day-21 (dig raw CNAME, HTTP 409 live); conf 58 holds; no verification TXT; HUM
- LEARN: REJECTED MISCONFIG @ all: 21:15Z cycle — chunk diff + route-literal scan + CNAME re-check yield zero deltas; all passive monitors confirmed converged/closed.
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: new build live 15:09Z 09-18 — chunk 0-mbmp1iqb6hj.js, route refs {/admin,/courses,/dashboard,/einladung,/passwort-neu,/pas
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 20+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-18 23:24:36 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: new build live 15:09Z 09-18 — chunk 0-mbmp1iqb6hj.js, route refs {/admin,/courses,/dashboard,/einladung,/passwort-neu,/pas
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 20+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-19 01:37:31 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: new build live 15:09Z 09-18 — chunk 0-mbmp1iqb6hj.js, route refs {/admin,/courses,/dashboard,/einladung,/passwort-neu,/pas
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 21+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-19 06:39:33 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST /auth/v1/token?gran
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: 06:37Z 09-19 — /login 200 no Set-Cookie, / 307→/login, chunk f916f314... unchanged; pre-auth surface day-22 stable, exhausted.
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 06:37Z 09-19 dig — CNAME→cname.perspective-dns.com day-22, HTTP 409 live; conf 58 holds; HUMAN claim-attempt only proof pat
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 holds 06:37Z 09-19 — probeable, zero buckets.
- LEARN: REJECTED MISCONFIG @ all: 06:37Z 09-19 cycle — chunk hash + route gate + CNAME re-check yield zero deltas; all passive monitors confirmed converged/closed day-2
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) rejected as "Invalid API key" across all endpoints; sb_publishable_ format acce
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: new build live 15:09Z 09-18 — chunk 0-mbmp1iqb6hj.js, route refs {/admin,/courses,/dashboard,/einladung,/passwort-neu,/pas
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 21+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-19 11:36:54 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange bearer tokens via POST /auth/v1/token?grant_typ
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- LEARN: REJECTED MISCONFIG @ kurs.onecode.de: new deploy 11:33Z 09-19 (boot 2a8cgfwu75lsu, module 4310-_brt1a3g) adds pre-auth /datenschutz+/rechtliches — static legal 
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /datenschutz + /rechtliches now pre-auth 200; /admin,/dashboard 307→/login unchanged; pre-auth surface = /login,/passwort-verge
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: new build live 15:09Z 09-18 — chunk 0-mbmp1iqb6hj.js, route refs {/admin,/courses,/dashboard,/einladung,/passwort-neu,/pas
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 22+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-19 14:52:08 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange bearer tokens via POST /auth/v1/token?grant_typ
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: 14:50Z 09-19 — /login 200 no Set-Cookie, /datenschutz + /rechtliches 200 (11:33Z build live-verified), chunk f916f314 unchanged
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 14:50Z dig — CNAME→cname.perspective-dns.com day-23, HTTP 409 live; conf 58 holds; HUMAN claim-attempt only proof path.
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds 14:50Z; Bearer-only now 400 "Invalid Compact JWS" → apikey header required; pl
- LEARN: REJECTED MISCONFIG @ all: 14:50Z cycle — legal pages static (zero /api), chunk unchanged, all passive monitors closed/converged day-23.
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: new deploy 11:33Z 09-19 adds pre-auth /datenschutz + /rechtliches — static legal pages, no form, no API, zero new surface
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /datenschutz + /rechtliches now pre-auth 200; /admin,/dashboard 307→/login unchanged; pre-auth surface = /login,/passwort-verge
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 22+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-19 17:53:37 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange bearer tokens via POST /auth/v1/token?grant_type=pa
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- LEARN: REJECTED MISCONFIG @ all: 17:52Z cycle — chunk hash f916f314 unchanged, module 4310-_brt1a3g route literals consumed, cto CNAME day-23 stable, /login 200; zero 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: mixed-generation co-residency (old chunk 0-lpao5_i9htd.js + new) still served pre-auth; no runtime exposure — all referenc
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: new deploy 11:33Z 09-19 adds pre-auth /datenschutz + /rechtliches — static legal pages, no form, no API, zero new surface
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /datenschutz + /rechtliches now pre-auth 200; /admin,/dashboard 307→/login unchanged; pre-auth surface = /login,/passwort-verge
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 23+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-19 20:23:14 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange bearer tokens via POST /auth/v1/token?grant_type=pa
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- LEARN: REJECTED MISCONFIG @ all: 20:21Z 09-19 cycle — chunk hash f916f314 unchanged, route gates stable (/login 200, legal 200, /admin 307), cto CNAME day-23, kurs CNA
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: new deploy 11:33Z 09-19 adds pre-auth /datenschutz + /rechtliches — static legal pages, no form, no API, zero new surface
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /datenschutz + /rechtliches now pre-auth 200; /admin,/dashboard 307→/login unchanged; pre-auth surface = /login,/passwort-verge
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 23+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-19 22:32:25 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange bearer tokens via POST /auth/v1/token?grant_type=pa
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- LEARN: REJECTED MISCONFIG @ all: 22:29Z 09-19 cycle — chunk set byte-identical, route gates stable (/login 200, legal 200, /admin 307), cto CNAME day-24 (409/1001 + TL
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: live re-confirm 22:29Z 09-19 — HTTP 80 → 409, HTTPS 443 handshake-fail, CNAME→cname.perspective-dns.com (104.18.2.73/3.73),
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: new deploy 11:33Z 09-19 adds pre-auth /datenschutz + /rechtliches — static legal pages, no form, no API, zero new surface
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /datenschutz + /rechtliches now pre-auth 200; /admin,/dashboard 307→/login unchanged; pre-auth surface = /login,/passwort-verge
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 23+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: new deploy 11:33Z 09-19 adds pre-auth /datenschutz + /rechtliches — static legal pages, no form, no API, zero new surface
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /datenschutz + /rechtliches now pre-auth 200; /admin,/dashboard 307→/login unchanged; pre-auth surface = /login,/passwort-verge
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 23+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: new deploy 11:33Z 09-19 adds pre-auth /datenschutz + /rechtliches — static legal pages, no form, no API, zero new surface
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /datenschutz + /rechtliches now pre-auth 200; /admin,/dashboard 307→/login unchanged; pre-auth surface = /login,/passwort-verge
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 23+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-20 00:25:15 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange bearer tokens via POST /auth/v1/token?grant_type=pa
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute the BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both hashed bearer tokens via POST /auth/v1/tok
- LEARN: REJECTED MISCONFIG @ all: 09-20 cycle — kurs /login 200+/ 307, cto CNAME→cname.perspective-dns.com day-25 (409/1001 via --resolve), storage 200 `[]`, kurs CNAME
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: live re-confirm 09-20 — HTTP 80 → 409, HTTPS 443 handshake-fail, CNAME→cname.perspective-dns.com (104.18.2.73/3.73), no ver
- LEARN: ACCEPTED MISCONFIG @ kurs.onecode.de: new deploy 11:33Z 09-19 adds pre-auth /datenschutz + /rechtliches — static legal pages, no form, no API, zero new surface
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /datenschutz + /rechtliches now pre-auth 200; /admin,/dashboard 307→/login unchanged; pre-auth surface = /login,/passwort-verge
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 23+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-20 05:27:54 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange bearer tokens via POST aygnpacdkgtsfnhgcyjc.supabas
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST /auth/v1/token?grant_ty
- LEARN: REJECTED MISCONFIG @ all: 05:27Z 09-20 cycle — /login 200 (no Set-Cookie, iad1), chunk set byte-identical to 09-19 22:29Z, cto CNAME day-26 (TXT zero), kurs CNA
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 25+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-20 10:11:35 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung; exchange bearer tokens via POST aygnpacdkgtsfnhgcyjc.supabas
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: REJECTED MISCONFIG @ all: 10:07Z 09-20 cycle — /login 200, chunk set byte-identical to 09-19, cto CNAME day-27, storage 200 `[]`; zero deltas; passive recon ful
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 25+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-20 14:23:14 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung; exchange bearer tokens via POST https://aygnpacdkgtsfnhgcyjc
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: REJECTED MISCONFIG @ all: 09-20 cycle — /login 200, /datenschutz 200, /admin 307, storage 200 `[]`, cto CNAME→cname.perspective-dns.com day-27 (409/1001); zero 
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 25+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-20 17:37:25 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung; exchange bearer tokens via POST https://aygnpacdkgtsfnhgcyjc
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: REJECTED MISCONFIG @ all: 09-20 cycle — /login 200, /datenschutz 200, /admin 307, storage 200 `[]`, cto CNAME→cname.perspective-dns.com day-27 (409/1001); zero 
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 25+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-20 19:48:58 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 27+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-20 22:22:08 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Confirm authorization, then execute BOLA escalation — 2 invited synthetic accounts via kurs.onecode.de/einladung; exchange bearer tokens via POST https:/
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: REJECTED MISCONFIG @ all: 09-20 cycle — /login 200, /datenschutz 200, /admin 307, storage 200 `[]`, cto CNAME→cname.perspective-dns.com day-27 (409/1001); zero 
- LEARN: REJECTED MISCONFIG @ all: 22:18Z 09-20 cycle — /login 200, /datenschutz 200, /admin 307, chunk sha256 f916f314 unchanged, storage 200 `[]`, kurs CNAME ki8dqcf6 
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 27+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-21 00:22:12 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (unchanged) (from art/lead_bigpickle.txt)
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Confirm bug-bounty authorization for two invited synthetic accounts, then execute BOLA escalation — 2 invites via kurs.onecode.de/einladung; exchange bea
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: 00:20Z 09-21 — /login 200 (railway-hikari, lax1.ez9k), /datenschutz /rechtliches 200, /admin / 307; chunk sha256 f916f314 uncha
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: dig 00:21Z 09-21 — CNAME→cname.perspective-dns.com day-29, TXT zero at host, A 104.18.2.73/3.73; 409/1001 + TLS-fail persis
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` re-confirmed 00:21Z 09-21 — endpoint probeable, zero buckets; unchanged.
- LEARN: REJECTED MISCONFIG @ kurs.onecode.de: new woff2 preload `75affa71d1e2f6a7-s.p.17-aodiw50953.woff2` (200, 34KB) — static font artifact, main chunk byte-identical
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 27+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-21 05:13:57 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Confirm bug-bounty authorization for two invited synthetic accounts, then execute BOLA escalation — 2 invites via kurs.onecode.de/einladung; exchange bea
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 27+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 27+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 29+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-21 10:55:56 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Confirm bug-bounty authorization for two invited synthetic accounts, then execute BOLA escalation — 2 invites via kurs.onecode.de/einladung; exchange bea
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 29+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-21 17:01:19 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Confirm bug-bounty authorization for two invited synthetic accounts, then execute BOLA escalation — 2 invites via kurs.onecode.de/einladung; exchange bea
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: dig day-30 09-21 — CNAME→cname.perspective-dns.com stable, TXT zero, A 104.18.2.73/3.73; HTTP 409/1001 + TLS handshake-fail
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login + legal pages 200, /admin etc 307; chunk sha256 f916f314 byte-identical; pre-auth surface stable, exhausted; no new cook
- LEARN: REJECTED MISCONFIG @ all: no deploy signal since 09-19 11:33Z build; zero deltas across same-day cycles; passive recon fully converged day-30, no probe value wi
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 29+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-21 20:56:27 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Confirm bug-bounty authorization for two invited synthetic accounts, then execute BOLA escalation — 2 invites via kurs.onecode.de/einladung; exchange bea
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 29+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-22 00:00:02 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Confirm bug-bounty authorization for two invited synthetic accounts, then execute BOLA escalation — 2 invites via kurs.onecode.de/einladung; exchange bea
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 30+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-22 04:42:26 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Confirm bug-bounty authorization for two invited synthetic accounts, then execute BOLA escalation — 2 invites via kurs.onecode.de/einladung; exchange bea
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: live 09-22 dig/re-probe — CNAME→cname.perspective-dns.com day-31, TXT zero, HTTP 409/1001; conf 58 holds; HUMAN claim-attem
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200, chunk sha256 f916f314 byte-identical, route set unchanged; pre-auth surface stable/exhausted day-31; no new cookie/
- LEARN: REJECTED MISCONFIG @ all: no deploy since 09-19 11:33Z build; zero deltas across 09-22 probes; passive recon fully converged day-31, no probe value without a de
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 30+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-22 09:46:21 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Confirm bug-bounty authorization for two invited synthetic accounts, then execute BOLA escalation — 2 invites via kurs.onecode.de/einladung; exchange bea
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: 09:44Z 09-22 re-probe — /login 200, / 307→/login, legal pages 200, /admin 307, chunk sha256 f916f314 byte-identical; pre-auth s
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 09:44Z dig/re-probe — CNAME→cname.perspective-dns.com day-31, TXT zero, HTTP 409/1001; conf 58 holds; HUMAN claim-attempt o
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` re-confirmed 09:44Z 09-22 — probeable, zero buckets; unchanged.
- LEARN: REJECTED MISCONFIG @ all: no deploy since 09-19 11:33Z build; zero deltas across 09-22 probes; passive recon fully converged day-31, no probe value without a de
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 30+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-22 14:34:31 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Confirm bug-bounty authorization for two invited synthetic accounts, then execute BOLA escalation — 2 invites via kurs.onecode.de/einladung; exchange bea
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: 14:32Z 09-22 re-probe — /login 200 (iad1.fp5t/jfk1.aghq), / 307→/login, legal 200, /admin + /api/broadcast 307, chunk sha256 f9
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 14:32Z dig/re-probe — CNAME→cname.perspective-dns.com day-31 (A 104.18.2.73/3.73), TXT zero, HTTP 409/1001; conf 58 holds; 
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` re-confirmed 14:32Z 09-22 — probeable, zero buckets; unchanged.
- LEARN: REJECTED MISCONFIG @ all: no deploy since 09-19 11:33Z build; zero deltas across 09-22 probes; passive recon fully converged day-31, no probe value without a de
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 31+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-22 18:19:06 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 31+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-22 21:30:12 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 31+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-22 23:51:08 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 31+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-23 04:12:29 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 31+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-23 09:24:42 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange bearer tokens (POST https://aygnpacdkgtsfnhgcyjc.su
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 31+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-23 14:29:09 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: Both open leads are proof-gated, not probe-gated — report-only to bugs.olivermaicher.eu (BOLA + cto CNAME) unless real, authorized access is held: (a) tw
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: REJECTED MISCONFIG @ all: no deploy signal since 09-19 11:33Z; chunk sha256 f916f314 byte-identical; build-diff is event-triggered, not time-based — time-cadenc
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com day-33, 409/1001 + TLS-fail, TXT zero; conf 58 holds; HUMAN/consented proof path only.
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: pre-auth surface stable/exhausted day-33 = {/login,/passwort-vergessen,/datenschutz,/rechtliches} 200; all /api,/v1,/admin,/das
- LEARN: ACCEPTED AUTH @ aygnpacdkgtsfnhgcyjc.supabase.co: publishable-key anon-block platform-enforced (REST monitor closed after 26 probes); storage 200 `[]` zero buck
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 31+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-23 18:42:27 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS SELECT policy lacking user_id predicate (from art/lead_bigpickle.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 33+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-23 21:51:53 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS policy gap (from art/lead_nemotron3.txt)
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS SELECT policy lacking user_id predicate (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: both open leads are proof-gated, not probe-gated — report-only to bugs.olivermaicher.eu (BOLA RLS-gap + cto CNAME takeover) unless verified authorization
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: REJECTED MISCONFIG @ all: no deploy since 09-19 11:33Z; chunk sha256 f916f314 byte-identical; build-diff is event-triggered, not time-based — time-cadence probi
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: pre-auth surface stable/exhausted day-34 = {/login,/passwort-vergessen,/datenschutz,/rechtliches} 200; all /api,/v1,/admin,/das
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com day-34, 409/1001 + TLS-fail, TXT zero; conf 58 holds; HUMAN/consented proof path only.
- LEARN: ACCEPTED AUTH @ aygnpacdkgtsfnhgcyjc.supabase.co: publishable-key anon-block platform-enforced (REST monitor closed after 26 probes); storage 200 `[]` zero buck
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 33+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-24 00:23:06 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS SELECT policy lacking user_id predicate (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 34+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-24 05:09:00 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS SELECT policy lacking user_id predicate (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 34+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-24 10:13:41 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS SELECT policy lacking user_id predicate (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 34+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-24 15:18:24 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS SELECT policy lacking user_id predicate (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 34+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-24 19:20:24 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS SELECT policy lacking user_id predicate (from art/lead_nemotron3.txt)
- [58] cto.onecode.de: Dangling Perspective CNAME takeover on cto.onecode.de (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: escalate BOLA together with storage+bucket watches — request OneCode program consent + two platform-invited test accounts; on grant, POST token exchange 
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: 19:19Z 09-24 re-probe — /login 200 no Set-Cookie, / 307, main chunk f916f314 byte-identical day-36; no deploy, no cookie/sessio
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: 19:19Z — CNAME→cname.perspective-dns.com day-36, TXT zero, HTTP 409/1001; conf 58 holds; HUMAN claim-attempt only proof pat
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1: 200 `[]` holds day-36; confidence 35 parked below threshold.
- LEARN: REJECTED MISCONFIG @ all: no deploy signal since 09-19 11:33Z; chunk diff is event-triggered, not time-based — time-cadence probing has no value day-36.
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 34+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-24 22:35:08 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS SELECT policy lacking user_id predicate (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 34+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-25 00:49:56 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS SELECT policy lacking user_id predicate (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 37+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-25 06:03:32 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS SELECT policy lacking user_id predicate (from art/lead_nemotron3.txt)
- [65] kurs.onecode.de: Cross-tenant BOLA via Supabase RLS SELECT policy lacking user_id predicate (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: obtain two invited test accounts (AUTH_HELPED) → run BOLA test: login each via POST /auth/v1/token?grant_type=password, then GET https://aygnpacdkgtsfnhg
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 37+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-25 11:47:27 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS SELECT policy lacking user_id predicate (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 37+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-25 16:57:56 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS SELECT policy lacking user_id predicate (from art/lead_nemotron3.txt)
- [65] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/{profiles,enrollments,courses}: Cross-tenant BOLA via Supabase RLS SELECT policy lacking user_id predicate (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://kurs.onecode.de/dashboard?_rsc=k1 with headers `RSC: 1` and `Next-Router-State-Tree: %5B%22%22%2C%7B%7D%2Cnull%2Cnull%2Ctrue%5D` (no cookies,
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: REJECTED MISCONFIG @ kurs.onecode.de: versioned and debug path sweep (09-25 16:56Z) — /api/graphql, /api/v2/health, /api/internal, /api/docs, /openapi.json, /sw
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external URL fetch re-confirmed 400 at 16:56Z; remotePatterns still not permissive, no open-proxy primitive.
- LEARN: NO_DELTA @ kurs.onecode.de: main chunk sha256 f916f314ea61a8c58a055707fc63c251f38e8412ae7a08e6abd7500ec375abca byte-identical to the 09-19 11:33Z build, day-6 w
- LEARN: REJECTED OATH @ aygnpacdkgtsfnhgcyjc.supabase.co: /auth/v1/settings re-read 16:56Z shows all 26 external providers false, saml_enabled false, passkeys disabled 
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME cto.onecode.de → cname.perspective-dns.com confirmed day-38 with zero verification TXT; still unbound/reclaimable at 
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: pre-auth surface is exactly {/login, /passwort-vergessen, /datenschutz, /rechtliches} at 200; the sole RSC literal in the paylo
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 37+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-25 20:24:14 UTC
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS SELECT policy lacking user_id predicate (from art/lead_nemotron3.txt)
- [62] kurs.onecode.de/login: Session fixation via Supabase implicit-flow URL-fragment token injection on pre-auth pages (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: request one invited test account via `kurs.onecode.de/einladung` (plus a second identity for the victim's browser). This single unblock resolves both sur
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: pre-auth attack surface is now *characterized, not just enumerated* — all 13 current-build chunks plus the co-resident old chun
- LEARN: REJECTED AUTH @ kurs.onecode.de: RSC/segment negotiation, path-normalization (10 variants), and `X-Original-URL`/`X-Rewrite-URL`/`X-Forwarded-Prefix` desync all
- LEARN: REJECTED AUTH @ Supabase: `alg=none` and no-apikey bearer both rejected (403 `bad_jwt`, 401 `No API key found`) — signature validation is sound.
- LEARN: REJECTED MISCONFIG @ Supabase realtime: `/realtime/v1/websocket` upgrade returns 403 with the publishable key — the HTTP-GET 401 does generalize; realtime is cl
- LEARN: NO_DELTA @ kurs.onecode.de / cto.onecode.de: main chunk `f916f314ea61a8c5…` byte-identical (day-7, no deploy); cto CNAME + 409 stable day-39. Build-diffing must
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 38+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 

## RANKED HYPOTHESES 2026-09-25 23:34:33 UTC
- [66] kurs.onecode.de: Session fixation via application-code setSession() of an attacker-supplied token pair in the URL fragment (from art/lead_bigpickle.txt)
- [65] kurs.onecode.de: Post-auth cross-tenant BOLA via Supabase RLS SELECT policy lacking user_id predicate (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: request one invited test account via kurs.onecode.de/einladung (contact@onecode.de is public on the legal pages). That single credential is the only miss
- NEXT(hypotheses-nemotron3.txt): HUMAN: Execute BOLA escalation — provision two invited test accounts via kurs.onecode.de/einladung, exchange both bearer tokens via POST https://aygnpacdkgtsfnh
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: the fragment→session sink is first-party code (module 34891 HashSessionHandoff, current build), not merely a supabase-js defaul
- LEARN: REJECTED MISCONFIG @ kurs.onecode.de: no privileged Supabase key is shipped to the browser — 13 pre-auth chunks scanned, zero JWTs, zero service_role/secret/JWT
- LEARN: REJECTED AUTH @ kurs.onecode.de: no unauthenticated Server Action and no server-side credential handling on /login — the form carries no action/method/name attr
- LEARN: REJECTED OATH @ kurs.onecode.de: HashSessionHandoff's post-setSession redirect is a fixed two-entry map defaulting to "/" — the injected session cannot be redir
- LEARN: NO_DELTA @ cto.onecode.de / Supabase storage: CNAME→cname.perspective-dns.com with empty TXT and HTTP 409 at day-39; storage 200 with zero buckets; main chunk b
- LEARN: ACCEPTED AUTH @ kurs.onecode.de: /login 200 + / 307→/login unchanged; pre-auth surface stable, exhausted; no new cookie/session signal
- LEARN: ACCEPTED MISCONFIG @ cto.onecode.de: CNAME→cname.perspective-dns.com stable 39+ days; 409/1001 + TLS handshake-fail; unbound/reclaimable; conf 58, HUMAN confirm
- LEARN: ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: 200 `[]` holds — endpoint probeable, zero buckets
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: monitor formally closed 09-17 — 26 probes (503↔401), never 200+rows; publishable-key rejection p
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: 404 — no deployed functions
- LEARN: REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: 401 — auth required, no pre-auth exposure
- LEARN: REJECTED OATH @ kurs.onecode.de: all external providers false; whitelist-locked redirects
- LEARN: REJECTED AUTH @ kurs.onecode.de: x-middleware-subrequest bypass header (CVE-2025-29927) negative live 16:34Z-19:5xZ 09-16 — /api/v1/health + /dashboard still 30
- LEARN: REJECTED SSRF @ kurs.onecode.de/_next/image: external url fetch → 400; remotePatterns not permissive; no image-optimizer open-proxy primitive pre-auth
- LEARN: NEW INFO @ aygnpacdkgtsfnhgcyjc.supabase.co/*: JWT anon key format (eyJhbGci...) now rejected as "Invalid API key" across all endpoints; sb_publishable_ format 
