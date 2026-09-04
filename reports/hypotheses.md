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
