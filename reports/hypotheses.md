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
