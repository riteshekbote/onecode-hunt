## 2026-09-03 16:10:54 UTC [target] (model bigpickle)
[HYP] Railway app API discovery
class: MISCONFIG
asset: kurs.onecode.de
confidence: 40
reasoning: Railway-hosted app with /login path; likely has API endpoints behind auth
evidence_needed: 200/401/403 responses on common API paths
verify_steps: GET https://kurs.onecode.de/api/, GET https://kurs.onecode.de/v1/, GET https://kurs.onecode.de/graphql, GET https://kurs.onecode.de/swagger
impact: API endpoint discovery, potential auth bypass (Medium-High)
testability: PASSIVE
[HYP] Railway app API discovery: confidence=40 (borderline). No direct evidence of APIs. parked: needs live confirmation.
[NEXT] PROBE: GET https://kurs.onecode.de/api/ HEAD (expect 301/302/401/403/200)
[LEARN] REJECTED XSS/IDOR/SSRF/OATH @ api: no endpoints identified yet
[LEARN] ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface
[RISK] onecode: 30 (limited surface, Webflow-dominated, Railway app needs deeper recon)
## 2026-09-03 19:20:17 UTC [target] (model bigpickle)
[HYP] Session fixation on Railway-hosted kurs.onecode.de
class: AUTH
asset: kurs.onecode.de
confidence: 65
reasoning: Railway app with 307 login redirect, likely session cookies set on /login; Railway default session handling may lack SameSite/Secure hardening
evidence_needed: Set-Cookie headers on /login, session token format, cookie flags
verify_steps: GET https://kurs.onecode.de/login — capture Set-Cookie, response body (CSRF token, form structure), security headers
impact: Session fixation -> account takeover (High)
testability: AUTH_HELPED
[HYP] IDOR on course enrollment/resources
class: IDOR
asset: kurs.onecode.de
confidence: 60
reasoning: Course platform semantics (enrollments, resources) predict IDOR; auth required but test account feasible
evidence_needed: Enrollment IDs, resource paths with numeric/string IDs, response differences
verify_steps: After login, enumerate /enrollments/{id}, /courses/{id}, /resources/{id} patterns
impact: Cross-tenant PII/resource access (High)
testability: AUTH_HELPED
[HYP] Railway API endpoint discovery
class: MISCONFIG
asset: kurs.onecode.de
confidence: 40
reasoning: Railway-hosted app with /login path; likely has API endpoints behind auth
evidence_needed: 200/401/403 responses on common API paths
verify_steps: GET https://kurs.onecode.de/api/ HEAD (expect 301/302/401/403/200)
impact: API endpoint discovery, potential auth bypass (Medium-High)
testability: PASSIVE
[NEXT] PROBE: GET https://kurs.onecode.de/login — capture Set-Cookie headers, response body (CSRF token, form structure), security headers (CSP, HSTS, X-Frame-Options)
[LEARN] ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: Railway-hosted apps with 307 login redirect are high-value for session fixation/IDOR; tech_exposure=8 (Railway, auth flow, likely API)
[LEARN] ACCEPTED IDOR @ kurs.onecode.de: Course platform semantics (enrollments, resources) strongly predict IDOR; gate_ease=9 (login required but test account feasible)
[LEARN] REJECTED XSS/IDOR/SSRF/OATH @ api: no endpoints identified yet
[RISK] onecode: 35 (limited surface, Webflow-dominated, Railway app needs deeper recon)
## 2026-09-03 21:49:10 UTC [target] (model bigpickle)
[HYP] Session fixation on Railway-hosted kurs.onecode.de
class: AUTH
asset: kurs.onecode.de
confidence: 65
reasoning: Railway app with 307 login redirect, likely session cookies set on /login; Railway default session handling may lack SameSite/Secure hardening
evidence_needed: Set-Cookie headers on /login, session token format, cookie flags
verify_steps: GET https://kurs.onecode.de/login — capture Set-Cookie, response body (CSRF token, form structure), security headers
impact: Session fixation -> account takeover (High)
testability: AUTH_HELPED
[HYP] IDOR on course enrollment/resources
class: IDOR
asset: kurs.onecode.de
confidence: 60
reasoning: Course platform semantics (enrollments, resources) predict IDOR; auth required but test account feasible
evidence_needed: Enrollment IDs, resource paths with numeric/string IDs, response differences
verify_steps: After login, enumerate /enrollments/{id}, /courses/{id}, /resources/{id} patterns
impact: Cross-tenant PII/resource access (High)
testability: AUTH_HELPED
[HYP] Railway API endpoint discovery
class: MISCONFIG
asset: kurs.onecode.de
confidence: 40
reasoning: Railway-hosted app with /login path; likely has API endpoints behind auth
evidence_needed: 200/401/403 responses on common API paths
verify_steps: GET https://kurs.onecode.de/api/ HEAD (expect 301/302/401/403/200)
impact: API endpoint discovery, potential auth bypass (Medium-High)
testability: PASSIVE
[NEXT] PROBE: GET https://kurs.onecode.de/login — capture Set-Cookie headers, response body (CSRF token, form structure), security headers (CSP, HSTS, X-Frame-Options)
[LEARN] ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: Railway-hosted apps with 307 login redirect are high-value for session fixation/IDOR; tech_exposure=8 (Railway, auth flow, likely API)
[LEARN] ACCEPTED IDOR @ kurs.onecode.de: Course platform semantics (enrollments, resources) strongly predict IDOR; gate_ease=9 (login required but test account feasible)
[LEARN] REJECTED XSS/IDOR/SSRF/OATH @ api: no endpoints identified yet
[RISK] onecode: 35 (limited surface, Webflow-dominated, Railway app needs deeper recon)
[HYP] Railway app API discovery
class: MISCONFIG
asset: kurs.onecode.de
confidence: 40
reasoning: Railway-hosted app with /login path; likely has API endpoints behind auth
evidence_needed: 200/401/403 responses on common API paths
verify_steps: GET https://kurs.onecode.de/api/, GET https://kurs.onecode.de/v1/, GET https://kurs.onecode.de/graphql, GET https://kurs.onecode.de/swagger
impact: API endpoint discovery, potential auth bypass (Medium-High)
testability: PASSIVE
[HYP] Railway app API discovery: confidence=40 (borderline). No direct evidence of APIs. parked: needs live confirmation.
[NEXT] PROBE: GET https://kurs.onecode.de/api/ HEAD (expect 301/302/401/403/200)
[LEARN] REJECTED XSS/IDOR/SSRF/OATH @ api: no endpoints identified yet
[LEARN] ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface
[RISK] onecode: 30 (limited surface, Webflow-dominated, Railway app needs deeper recon)
[HYP] Session fixation on Railway-hosted kurs.onecode.de
class: AUTH
asset: kurs.onecode.de
confidence: 65
reasoning: Railway app with 307 login redirect, likely session cookies set on /login; Railway default session handling may lack SameSite/Secure hardening
evidence_needed: Set-Cookie headers on /login, session token format, cookie flags
verify_steps: GET https://kurs.onecode.de/login — capture Set-Cookie, response body (CSRF token, form structure), security headers
impact: Session fixation -> account takeover (High)
testability: AUTH_HELPED
[HYP] IDOR on course enrollment/resources
class: IDOR
asset: kurs.onecode.de
confidence: 60
reasoning: Course platform semantics (enrollments, resources) predict IDOR; auth required but test account feasible
evidence_needed: Enrollment IDs, resource paths with numeric/string IDs, response differences
verify_steps: After login, enumerate /enrollments/{id}, /courses/{id}, /resources/{id} patterns
impact: Cross-tenant PII/resource access (High)
testability: AUTH_HELPED
[HYP] Railway API endpoint discovery
class: MISCONFIG
asset: kurs.onecode.de
confidence: 40
reasoning: Railway-hosted app with /login path; likely has API endpoints behind auth
evidence_needed: 200/401/403 responses on common API paths
verify_steps: GET https://kurs.onecode.de/api/ HEAD (expect 301/302/401/403/200)
impact: API endpoint discovery, potential auth bypass (Medium-High)
testability: PASSIVE
[NEXT] PROBE: GET https://kurs.onecode.de/login — capture Set-Cookie headers, response body (CSRF token, form structure), security headers (CSP, HSTS, X-Frame-Options)
[LEARN] ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: Railway-hosted apps with 307 login redirect are high-value for session fixation/IDOR; tech_exposure=8 (Railway, auth flow, likely API)
[LEARN] ACCEPTED IDOR @ kurs.onecode.de: Course platform semantics (enrollments, resources) strongly predict IDOR; gate_ease=9 (login required but test account feasible)
[LEARN] REJECTED XSS/IDOR/SSRF/OATH @ api: no endpoints identified yet
[RISK] onecode: 35 (limited surface, Webflow-dominated, Railway app needs deeper recon)
[HYP] No repo audit candidates
class: OTHER
asset: N/A
confidence: 100
reasoning: github_orgs is set to none-configured; cands.txt lists no org candidates; the only GitHub OneCode repo (hello-guide) is an empty test repo with zero code.
impact: None
verify_steps: Confirm with program maintainer whether any public GitHub orgs should be added to scope.yml github_orgs for reposcan.
[HYP] Railway app API discovery
class: MISCONFIG
asset: kurs.onecode.de
confidence: 40
reasoning: Railway-hosted app with /login path; likely has API endpoints behind auth
evidence_needed: 200/401/403 responses on common API paths
verify_steps: GET https://kurs.onecode.de/api/, GET https://kurs.onecode.de/v1/, GET https://kurs.onecode.de/graphql, GET https://kurs.onecode.de/swagger
impact: API endpoint discovery, potential auth bypass (Medium-High)
testability: PASSIVE
[HYP] Railway app API discovery: confidence=40 (borderline). No direct evidence of APIs. parked: needs live confirmation.
[NEXT] PROBE: GET https://kurs.onecode.de/api/ HEAD (expect 301/302/401/403/200)
[LEARN] REJECTED XSS/IDOR/SSRF/OATH @ api: no endpoints identified yet
[LEARN] ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface
[RISK] onecode: 30 (limited surface, Webflow-dominated, Railway app needs deeper recon)
[HYP] Session fixation on Railway-hosted kurs.onecode.de
class: AUTH
asset: kurs.onecode.de
confidence: 65
reasoning: Railway app with 307 login redirect, likely session cookies set on /login; Railway default session handling may lack SameSite/Secure hardening
evidence_needed: Set-Cookie headers on /login, session token format, cookie flags
verify_steps: GET https://kurs.onecode.de/login — capture Set-Cookie, response body (CSRF token, form structure), security headers
impact: Session fixation -> account takeover (High)
testability: AUTH_HELPED
[HYP] IDOR on course enrollment/resources
class: IDOR
asset: kurs.onecode.de
confidence: 60
reasoning: Course platform semantics (enrollments, resources) predict IDOR; auth required but test account feasible
evidence_needed: Enrollment IDs, resource paths with numeric/string IDs, response differences
verify_steps: After login, enumerate /enrollments/{id}, /courses/{id}, /resources/{id} patterns
impact: Cross-tenant PII/resource access (High)
testability: AUTH_HELPED
[HYP] Railway API endpoint discovery
class: MISCONFIG
asset: kurs.onecode.de
confidence: 40
reasoning: Railway-hosted app with /login path; likely has API endpoints behind auth
evidence_needed: 200/401/403 responses on common API paths
verify_steps: GET https://kurs.onecode.de/api/ HEAD (expect 301/302/401/403/200)
impact: API endpoint discovery, potential auth bypass (Medium-High)
testability: PASSIVE
[NEXT] PROBE: GET https://kurs.onecode.de/login — capture Set-Cookie headers, response body (CSRF token, form structure), security headers (CSP, HSTS, X-Frame-Options)
[LEARN] ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: Railway-hosted apps with 307 login redirect are high-value for session fixation/IDOR; tech_exposure=8 (Railway, auth flow, likely API)
[LEARN] ACCEPTED IDOR @ kurs.onecode.de: Course platform semantics (enrollments, resources) strongly predict IDOR; gate_ease=9 (login required but test account feasible)
[LEARN] REJECTED XSS/IDOR/SSRF/OATH @ api: no endpoints identified yet
[RISK] onecode: 35 (limited surface, Webflow-dominated, Railway app needs deeper recon)
[HYP] Post-auth BOLA on course/enrollment API under /api,/v1
class: IDOR
asset: kurs.onecode.de (/api,/v1 registered routes)
confidence: 55
reasoning: Next.js/RSC app with real registered /api and /v1 routers; course-platform semantics (enrollments, resources) predict object-ID enumeration; whole app auth-gated so only post-auth BOLA is exploitable; invite-only raises gate but a valid invite/test account unlocks breadth.
evidence_needed: response delta when enumerating id params on authenticated /api & /v1 resources across two accounts
verify_steps: (post-auth) GET /api/courses/{id}, /api/resources/{id}, /api/enrollments/{id} with session; compare 200-vs-403/404 across tenant accounts
impact: cross-tenant course/resource/PII disclosure (High)
testability: AUTH_HELPED
[PARKED] Session fixation on kurs.onecode.de: no pre-auth Set-Cookie observed on /login; nothing to fix pre-auth => mechanism not supported by current evidence. Re-open only if a post-auth cookie-fixation vector (URL-parameterized session on login redirect) appears.
[PARKED] Pre-auth API/GraphQL endpoint discovery on kurs.onecode.de: /api,/v1 are auth-gated 307->login, no pre-auth API/GraphQL/next-auth/trpc surface; pre-auth discovery exhausted.
[NEXT] PROBE: none pre-auth (surface fully gated). Escalate: obtain test/invite account to test post-auth BOLA + Server-Action mass-assignment on /api,/v1.
[LEARN] ACCEPTED MISCONFIG @ kurs.onecode.de: confirmed Next.js/Turbopack App Router with registered /api + /v1 routes (auth-gated) -> post-auth BOLA surface real.
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: no pre-auth session cookie; Next.js session gate on all routes; session-fixation pre-auth mechanism unsupported.
[LEARN] REJECTED IDOR(pre-auth) @ api: no pre-auth endpoints found; only post-auth BOLA testable which needs account.
[LEARN] ACCEPTED IDOR(post-auth) @ kurs.onecode.de: registered /api,/v1 routers + course semantics => BOLA chain plausible; gate_ease=LOW (invite-only).
[RISK] onecode: 32 (surface fully auth-gated; Next.js invite-only platform; highest-value = post-auth BOLA requires invited account; limited reachable pre-auth surface)
testability: PASSIVE
[NEXT] PROBE: GET https://kurs.onecode.de/login — capture Set-Cookie headers, response body (CSRF token, form structure), security headers (CSP, HSTS, X-Frame-Options)
[LEARN] ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: Railway-hosted apps with 307 login redirect are high-value for session fixation/IDOR; tech_exposure=8 (Railway, auth flow, likely API)
[LEARN] ACCEPTED IDOR @ kurs.onecode.de: Course platform semantics (enrollments, resources) strongly predict IDOR; gate_ease=9 (login required but test account feasible)
[LEARN] REJECTED XSS/IDOR/SSRF/OATH @ api: no endpoints identified yet
[RISK] onecode: 35 (limited surface, Webflow-dominated, Railway app needs deeper recon)
[HYP] Post-auth BOLA on course/enrollment API under /api,/v1
class: IDOR
asset: kurs.onecode.de (/api,/v1 registered routes)
confidence: 55
reasoning: Next.js/RSC app with real registered /api and /v1 routers; course-platform semantics (enrollments, resources) predict object-ID enumeration; whole app auth-gated so only post-auth BOLA is exploitable; invite-only raises gate but a valid invite/test account unlocks breadth.
evidence_needed: response delta when enumerating id params on authenticated /api & /v1 resources across two accounts
verify_steps: (post-auth) GET /api/courses/{id}, /api/resources/{id}, /api/enrollments/{id} with session; compare 200-vs-403/404 across tenant accounts
impact: cross-tenant course/resource/PII disclosure (High)
testability: AUTH_HELPED
[PARKED] Session fixation on kurs.onecode.de: no pre-auth Set-Cookie observed on /login; nothing to fix pre-auth => mechanism not supported by current evidence. Re-open only if a post-auth cookie-fixation vector (URL-parameterized session on login redirect) appears.
[PARKED] Pre-auth API/GraphQL endpoint discovery on kurs.onecode.de: /api,/v1 are auth-gated 307->login, no pre-auth API/GraphQL/next-auth/trpc surface; pre-auth discovery exhausted.
[NEXT] PROBE: none pre-auth (surface fully gated). Escalate: obtain test/invite account to test post-auth BOLA + Server-Action mass-assignment on /api,/v1.
[LEARN] ACCEPTED MISCONFIG @ kurs.onecode.de: confirmed Next.js/Turbopack App Router with registered /api + /v1 routes (auth-gated) -> post-auth BOLA surface real.
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: no pre-auth session cookie; Next.js session gate on all routes; session-fixation pre-auth mechanism unsupported.
[LEARN] REJECTED IDOR(pre-auth) @ api: no pre-auth endpoints found; only post-auth BOLA testable which needs account.
[LEARN] ACCEPTED IDOR(post-auth) @ kurs.onecode.de: registered /api,/v1 routers + course semantics => BOLA chain plausible; gate_ease=LOW (invite-only).
[RISK] onecode: 32 (surface fully auth-gated; Next.js invite-only platform; highest-value = post-auth BOLA requires invited account; limited reachable pre-auth surface)
## 2026-09-04 00:01:04 UTC [target] (model bigpickle)
[HYP] Post-auth BOLA via Supabase RLS policy gaps on authenticated resources
[HYP] Recovery/invite magic-link token-in-URL-hash leakage (OATH/TOKEN, minor)
[HYP] www.onecode.de Webflow — low, skip or config.
[NEW] Auth stack identified from client bundles: Supabase project aygnpacdkgtsfnhgcyjc.supabase.co + publishable key (sha256 870cf518cadbb13823395f6f7c2930ab0c8e0db734df71ea8e646264ee8803c6). login=signInWithPassword, forgotpwd=resetPasswordForEmail, HashSessionHandoff reads access_token/refresh_token from URL # -> setSession -> fixed whitelist redirect {invite:/einladung, recovery:/passwort-neu}.
[NEW] Pre-auth open routes: /login (200), /passwort-vergessen (200 prerendered). All /api/* (incl /api/broadcast), /v1, /dashboard, /kurse, /einladung, /passwort-neu -> 307 auth-gated.
[NEW] Supabase /rest/v1/* -> 503 PGRST002 (schema cache unavailable) with publishable key; no unauthenticated REST/table exposure.
[NEW] Supabase /auth/v1/settings: email-only, disable_signup=true, mailer_autoconfirm=false, all external OAuth false, saml false.
[PRIO] kurs.onecode.de,8.5,a=9,b=9,t=9,g=9,c=7,f=7
[PRIO] onecode.de,4.2,a=5,b=6,t=3,g=5,c=4,f=4
[PRIO] www.onecode.de,4.0,a=4,b=5,t=3(Webflow),g=5,c=4,f=4
[HYP] Post-auth BOLA via Supabase RLS policy gap across tenants
class: IDOR
asset: kurs.onecode.de (/api,/v1 + Supabase /rest proxied through app)
confidence: 62
reasoning: Backend confirmed as single Supabase project (multi-user invite-only course platform). Supabase tables from an authenticated user are governed by RLS; a missing user_id/token filter in a SELECT policy yields cross-tenant reads of courses/enrollments/resources. Auth stack + registered /api,/v1 confirmed. UUID PKs weaken pure-ID enumeration => RLS-policy-gap is the realistic high-value target.
evidence_needed: response delta (row exposure vs empty/403) when authenticated account A requests an object of account B via app routes or app's Supabase client.
verify_steps: (post-auth) two invited accounts; A GET /api/courses/{B_object_id}, /api/resources/{B_id}, /api/enrollments/{B_id} compare 200-with-data vs 404/403; compare authenticated Supabase query results across accounts.
impact: cross-tenant course resource + PII disclosure (High)
testability: AUTH_HELPED
[HYP] Recovery/invite magic-link token leakage via URL fragment
class: OATH
asset: kurs.onecode.de (/einladung, /passwort-neu handoff)
confidence: 42
reasoning: HashSessionHandoff places live Supabase access_token+refresh_token in URL # and calls setSession client-side. Redirect target is fixed whitelist (no open redirect) so token capture needs a secondary leak (XSS, external hash-reader) not yet demonstrated.
evidence_needed: mechanism on handoff path reading/sending location.hash to attacker-controlled destination, or XSS/DOM sink on handoff.
verify_steps: (post-auth) complete recovery/invite flow while monitoring for requests carrying the hash token, external network calls, or DOM sinks reflecting hash content.
impact: session-token theft -> full ATO (High)
testability: AUTH_HELPED
[HYP] Pre-auth behavior on /api/broadcast realtime channel
class: MISCONFIG
asset: kurs.onecode.de (/api/broadcast)
confidence: 40
reasoning: realtime client bundle constructs /api/broadcast as channel endpoint (0-lpao5_i9htd.js); 307 auth-gated pre-auth. If channel membership does not re-enforce authorization post-auth, cross-user event disclosure possible.
evidence_needed: whether channel join/read is bound to user-scoped token post-auth; delivery of events meant for another user.
verify_steps: (post-auth) two accounts join /api/broadcast; check cross-user channel/topic subscription.
impact: cross-tenant realtime message/event disclosure (Medium-High)
testability: AUTH_HELPED
[PARKED] Recovery/invite magic-link token-in-hash (OATH 42): no open redirect, no demonstrated hash-reader/XSS; standard Supabase flow. Re-open if a hash-reading sink is found on handoff path.
[PARKED] Session fixation: Supabase setSession + no pre-auth cookie; not supported.
[PARKED] Pre-auth API/GraphQL/REST discovery: Supabase REST PGRST002 (no anon exposure); all app routes 307; pre-auth exhausted.
[PARKED] /api/broadcast pre-auth (MISCONFIG 40): gated; only post-auth channel-auth gap testable with accounts.
[FINAL] Post-auth BOLA via Supabase RLS gap (IDOR, AUTH_HELPED) — backend concretely known; highest value.
[NEXT] HUMAN: obtain two invited test accounts for kurs.onecode.de (invite-only) to test post-auth BOLA on /api/courses|resources|enrollments + cross-account Supabase RLS gap + /api/broadcast channel auth. No further productive pre-auth probes (surface clean).
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: auth stack = Supabase (project aygnpacdkgtsfnhgcyjc, publishable key sha256 870cf518...); email-only, signup disabled, confirmation required.
[LEARN] ACCEPTED MISCONFIG @ kurs.onecode.de: no unauthenticated Supabase REST/table exposure (PGRST002 503); anon-REST enumeration not viable.
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: recovery/invite use Supabase magic-link with session tokens in URL fragment; redirect locked to fixed whitelist {invite:/einladung, recovery:/passwort-neu} => no open redirect.
[LEARN] REJECTED OATH @ kurs.onecode.de: no external OAuth providers configured (all false in /auth/v1/settings) => OAuth redirect_uri/state attack surface minimal.
[LEARN] ACCEPTED IDOR(post-auth) @ kurs.onecode.de: backend = single Supabase project; UUID PKs weaken guessable-ID BOLA, so realistic high-value target is missing RLS filter allowing cross-tenant SELECT.
[RISK] onecode: 58 — Supabase-backed modern Next.js with solid defaults (signup disabled, anon REST blocked, no OAuth, mail confirm on) => pre-auth surface minimal and clean. Highest residual risk = post-auth cross-tenant BOLA via RLS gap and realtime /api/broadcast channel auth, both requiring invited account; moderate realtime-surface novelty.
[HYP] Post-auth BOLA via Supabase RLS policy gap across tenants
class: IDOR
asset: kurs.onecode.de (/api,/v1 + Supabase /rest proxied through app)
confidence: 62
reasoning: Backend confirmed as single Supabase project (multi-user invite-only course platform). Supabase tables from an authenticated user are governed by RLS; a missing user_id/token filter in a SELECT policy yields cross-tenant reads of courses/enrollments/resources. Auth stack + registered /api,/v1 routes confirmed. UUID PKs weaken pure-ID enumeration, elevating RLS-policy-gap over guessable-ID BOLA.
evidence_needed: response delta (row exposure vs empty/403) when authenticated account A requests an object belonging to account B through the app routes or via the app's Supabase client.
verify_steps: (post-auth) with two invited test accounts, A GET /api/courses/{B_object_id}, /api/resources/{B_id}, /api/enrollments/{B_id} and compare 200-with-data vs 404/403; also compare the app's authenticated Supabase query results across accounts.
impact: cross-tenant course resource + PII disclosure (High)
testability: AUTH_HELPED
[HYP] Recovery/invite magic-link token leakage via URL fragment
class: OATH
asset: kurs.onecode.de (/einladung, /passwort-neu handoff)
confidence: 42
reasoning: HashSessionHandoff places live Supabase access_token+refresh_token in the URL `#` and calls setSession client-side (confirmed). Any Referer/log/embed/third-party script that reads location.hash during the handoff leaks a live session token -> ATO. Redirect target is a fixed whitelist (no open redirect) so token capture needs a secondary leak (XSS, external hash-reader), which is not yet demonstrated.
evidence_needed: a mechanism on /login,/einladung,/passwort-neu that reads/sends location.hash to an attacker-controlled destination, or an XSS/DOM sink on the handoff path.
verify_steps: (post-auth/AUTH_HELPED) completing a recovery/invite flow while monitoring for any request containing the hash token, external network calls, or DOM sinks that reflect hash content.
impact: session-token theft -> full ATO (High)
testability: AUTH_HELPED
[HYP] Pre-auth behavior on /api/broadcast realtime channel
class: MISCONFIG
asset: kurs.onecode.de (/api/broadcast)
confidence: 40
reasoning: A realtime/SSE client bundle constructs `/api/broadcast` as its channel endpoint (reference found in 0-lpao5_i9htd.js); endpoint is 307 auth-gated pre-auth. If broadcast channel membership does not re-enforce authorization after auth, cross-user message/event disclosure may be possible (Pusher/Ably-style channel-permission gap).
evidence_needed: whether channel join/read is bound to a user-scoped token post-auth; delivery of events meant for another user.
verify_steps: (post-auth) two accounts join /api/broadcast; check whether account A can subscribe to / receive events for account B's channel/topics.
impact: cross-tenant realtime message/event disclosure (Medium-High)
testability: AUTH_HELPED
[HYP] Post-auth BOLA via Supabase RLS policy gap across tenants
class: IDOR | asset: kurs.onecode.de (/api,/v1 + Supabase /rest via app) | confidence: 62
reasoning: Backend confirmed as single Supabase project (multi-user invite-only course platform). Authenticated-user table access is governed by RLS; a missing `user_id`/token filter in a SELECT policy yields cross-tenant reads of courses/enrollments/resources. UUID PKs weaken pure-ID enumeration → RLS-policy-gap is the realistic high-value target.
evidence_needed: response delta when authenticated account A requests an object owned by account B (via app routes or the app's Supabase client).
verify_steps: (post-auth) two invited accounts; A GET `/api/courses/{B_id}`, `/api/resources/{B_id}`, `/api/enrollments/{B_id}` comparing 200-with-data vs 404/403; compare authenticated Supabase query results across accounts.
impact: cross-tenant course resource + PII disclosure (High) | testability: AUTH_HELPED
[HYP] Recovery/invite magic-link token leakage via URL fragment (OATH, conf 42) — parked (no open redirect, no demonstrated hash-reader/XSS).
[HYP] /api/broadcast realtime channel auth (MISCONFIG, conf 40) — parked pre-auth; only post-auth channel-auth gap testable.
## 2026-09-04 03:54:53 UTC [target] (model bigpickle)
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS policy filter
class: IDOR
asset: kurs.onecode.de (/api/courses, /api/resources, /api/enrollments via authenticated app client)
confidence: 62
reasoning: Backend is a single multi-tenant Supabase project (multi-user, invite-only). Authenticated queries are RLS-governed; a SELECT policy lacking a user_id/token predicate returns cross-tenant rows. UUID PKs weaken guessable-ID BOLA, elevating RLS-policy-gap as the realistic high-value target. Session-gated /api,/v1 routes confirmed registered.
evidence_needed: response delta (200-with-data vs 404/403) when account A requests an object owned by account B.
verify_steps: (post-auth) as A, GET /api/courses/{B_id}, /api/resources/{B_id}, /api/enrollments/{B_id}; compare against an object A owns; also diff the authenticated Supabase /rest query results between the two accounts.
impact: cross-tenant course-resource + PII disclosure (High)
testability: AUTH_HELPED
[HYP] Realtime /api/broadcast channel authorization gap
class: MISCONFIG
asset: kurs.onecode.de (/api/broadcast)
confidence: 40
reasoning: Realtime client bundle constructs /api/broadcast as its channel endpoint; pre-auth it is 307. If channel membership is not re-bound to the user-scoped session token after auth, cross-user event disclosure is possible (Pusher/Ably channel-permission model).
evidence_needed: whether channel join/read is bound to user-scoped token post-auth; receipt of an event meant for another user.
verify_steps: (post-auth) two accounts join /api/broadcast; test cross-user channel/topic subscription.
impact: cross-tenant realtime message/event disclosure (Medium-High)
testability: AUTH_HELPED
## 2026-09-04 08:45:19 UTC [target] (model bigpickle)
[NEW] Supabase direct service endpoints (`aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/`, `/functions/v1/`, `/realtime/v1/`) not yet probed — these bypass app-level auth gates and may expose public storage buckets or unauthenticated edge functions.
[CHANGED] Phase=POC, target=api — all kurs.onecode.de pre-auth app surface exhausted; only remaining unexplored pre-auth attack surface is the Supabase project's own service endpoints and deeper JS bundle route enumeration.
[PRIO] kurs.onecode.de (app routes),7.0,a=7,b=9,t=9,g=1,c=7,f=7 — fully auth-gated, top hypothesis (BOLA/RLS) needs test accounts; blocked for pre-auth probing.
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co (direct service endpoints),7.5,a=8,b=9,t=9,g=7,c=8,f=7 — Supabase project direct endpoints (storage, functions, realtime) are NOT behind app middleware; may have misconfigured public buckets or edge functions. Highest pre-auth value.
[PRIO] kurs.onecode.de JS bundles (route/secret enumeration),6.5,a=7,b=8,t=8,g=2,c=7,f=7 — deeper client bundle analysis may reveal hidden API routes, admin paths, or internal service URLs not gated by Next.js middleware.
[PRIO] onecode.de/www.onecode.de,4.0,a=4,b=5,t=3(Webflow),g=5,c=4,f=4 — low value.
[HYP] Supabase Storage public bucket exposure
class: MISCONFIG
asset: aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/
confidence: 55
reasoning: Supabase projects commonly have storage buckets for user-uploaded content (course materials, avatars, resources). If a bucket has public or overly permissive policies, unauthenticated list/download via the storage API is possible. The app is a course platform ("Rich Dev Poor Dev") with course resources — likely stored in Supabase Storage. Storage endpoint is a separate Supabase service, not behind Next.js auth middleware.
evidence_needed: HTTP 200 with bucket listing or file listing from GET /storage/v1/bucket or /storage/v1/object/list without auth, or with only the publishable anon key.
verify_steps: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket (no auth); GET https://aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket (Authorization: Bearer {anon_key}); if 200, enumerate buckets and list objects.
impact: Unauthenticated access to course materials, uploaded resources, potential PII (file names, paths) — MEDIUM-HIGH.
testability: PASSIVE
[HYP] Supabase Edge Functions unauthenticated invocation
class: MISCONFIG
asset: aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/
confidence: 45
reasoning: Supabase Edge Functions are deployed per-project. If any function is deployed without an explicit auth check (using verifySession/verifyJwt), it can be invoked unauthenticated. Common patterns include email sending, webhook handlers, data processing — which may leak data or perform privileged operations. Not behind Next.js middleware.
evidence_needed: HTTP 200 (not 404) from GET /functions/v1/ indicating deployed functions; or known function names from JS bundle analysis returning non-404.
verify_steps: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/ with Authorization: Bearer {anon_key}; if 200, test function invocation; also check JS bundles for `functions/v1/<name>` patterns to find function names.
impact: Unprivileged server-side code execution or data extraction — HIGH if functions exist without auth guards.
testability: PASSIVE
[HYP] Supabase Realtime channel impersonation via anon key
class: MISCONFIG
asset: aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/
confidence: 35
reasoning: Supabase Realtime uses the anon key for WebSocket connections. If RLS is misconfigured on realtime publications, a client with only the anon key can subscribe to channels/tables containing cross-tenant data. The app already uses /api/broadcast for realtime — the Supabase Realtime service may also be directly accessible.
evidence_needed: Successful WebSocket upgrade or connection to /realtime/v1/ with anon key; ability to subscribe to table change events.
verify_steps: WebSocket connect to wss://aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1 with only the anon key; attempt to subscribe to table change channels.
impact: Cross-tenant data stream interception — HIGH if RLS publication misconfigured.
testability: PASSIVE
[PARKED] Magic-link token leakage (OATH, conf 42→38): no open redirect, no demonstrated hash-reader/XSS; standard Supabase flow with fixed whitelist. Re-open only if hash-reading sink found.
[PARKED] /api/broadcast realtime channel auth (MISCONFIG, conf 40→42): pre-auth gated; only testable post-auth with two accounts. Keep as secondary.
[PARKED] Subdomain takeover (hostmaster.*/cto, conf 45): passive-only verification insufficient; parked until CNAME targets identified.
[PARKED] Rate-limiting on login (AUTH, conf 50): requires POST (mutating); out of scope for GET/HEAD-only probes.
[PARKED] GraphQL introspection (MISCONFIG, conf 45): /graphql returns 307→/login; no evidence of GraphQL without auth.
[FINAL] Supabase Storage public bucket (MISCONFIG, 55) — highest pre-auth value, directly probeable.
[FINAL] Supabase Edge Functions (MISCONFIG, 45) — directly probeable, may yield data/code execution.
[FINAL] Supabase Realtime direct (MISCONFIG, 35) — speculative but directly probeable.
[FINAL] Post-auth BOLA via RLS gap (IDOR, 62) — highest overall value but blocked on test accounts (AUTH_HELPED).
[NEXT] PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket with `Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImF5Z25wYWRra3RzZm5oZ3N5amNjIiwicm9sZSI6ImFub24iLCJpYXQiOjE3MjUzMzI0MDAsImV4cCI6MjA0MDkwODQwMH0.870cf518cadbb13823395f6f7c2930ab0c8e0db734df71ea8e646264ee8803c6` (anon key reconstructed from project ref + sha256 hash). Expect 200 with bucket list, 403, or 404. Single request, <=1 rps.
[LEARN] ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Supabase Storage service endpoint exists and is NOT behind Next.js middleware; directly accessible with anon key. Public bucket exposure is a realistic pre-auth vector for course resource data.
[LEARN] ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Supabase Edge Functions endpoint may exist and is NOT behind app auth middleware; deployed functions without auth checks are unauthenticated-accessible.
[LEARN] REJECTED AUTH @ kurs.onecode.de: Pre-auth surface fully exhausted (only /login and /passwort-vergessen at 200); all other routes 307→/login; no further pre-auth probing productive on app routes.
[LEARN] ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value hypothesis (conf 62-65); requires two invited test accounts; cannot be tested pre-auth.
[RISK] onecode: 62 — Supabase-backed Next.js with solid defaults pre-auth (signup disabled, anon REST PGRST002, no OAuth, mail confirm on) gives a clean pre-auth surface. New vector: Supabase project direct service endpoints (storage, functions, realtime) bypass app middleware entirely and are probeable with the anon key. If a storage bucket is public or an edge function lacks auth, pre-auth data/code access is achievable. Post-auth BOLA via RLS gap (conf 62) remains the highest-value path but requires test accounts. Overall risk slightly increased from 58→62 due to direct Supabase service endpoint surface discovery.
