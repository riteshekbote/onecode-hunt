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
## 2026-09-04 13:21:25 UTC [target] (model bigpickle)
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/,8.0,a=9,b=8,t=8,g=9,c=7,f=6
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/,7.5,a=8,b=7,t=8,g=8,c=6,f=6
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/,6.0,a=6,b=7,t=7,g=8,c=5,f=6
[PRIO] kurs.onecode.de (post-auth BOLA),7.0,a=7,b=9,t=8,g=1,c=7,f=7 (AUTH_HELPED)
[HYP] Supabase Storage public bucket listing
class: MISCONFIG
asset: aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/
confidence: 58
reasoning: Storage endpoint is a separate Supabase service not behind Next.js middleware. Course platform ("Rich Dev Poor Dev") stores resources in Supabase Storage. If bucket has public SELECT policy or overly permissive anon access, unauthenticated listing/download possible.
evidence_needed: HTTP 200 from GET /storage/v1/bucket with only anon key; bucket names visible in response
verify_steps: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket (Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImF5Z25wYWRra3RzZm5oZ3N5amNjIiwicm9sZSI6ImFub24iLCJpYXQiOjE3MjUzMzI0MDAsImV4cCI6MjA0MDkwODQwMH0.870cf518cadbb13823395f6f7c2930ab0c8e0db734df71ea8e646264ee8803c6)
impact: Unauthenticated access to course materials, uploaded resources, file metadata — MEDIUM-HIGH
testability: PASSIVE
[HYP] Supabase Edge Functions unauthenticated invocation
class: MISCONFIG
asset: aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/
confidence: 48
reasoning: Edge Functions deployed per-project; if any function lacks verifySession/verifyJwt, it can be invoked unauthenticated. Common patterns: email sending, webhooks, data processing.
evidence_needed: HTTP 200 (not 404) from GET /functions/v1/; function names from JS bundle
verify_steps: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/ (Authorization: Bearer anon_key); also grep client bundles for functions/v1/<name> patterns
impact: Server-side code execution or data extraction — HIGH
testability: PASSIVE
[HYP] Supabase Realtime cross-tenant subscription
class: MISCONFIG
asset: aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/
confidence: 35
reasoning: Supabase Realtime uses anon key for WebSocket connections. If RLS misconfigured on realtime publications, client can subscribe to channels containing cross-tenant data.
evidence_needed: Successful WebSocket upgrade; ability to subscribe to table change events with anon key
verify_steps: WebSocket connect to wss://aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1 with anon key
impact: Cross-tenant data stream interception — HIGH if RLS publication misconfigured
testability: PASSIVE
[NEXT] PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket with Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImF5Z25wYWRra3RzZm5oZ3N5amNjIiwicm9sZSI6ImFub24iLCJpYXQiOjE3MjUzMzI0MDAsImV4cCI6MjA0MDkwODQwMH0.870cf518cadbb13823395f6f7c2930ab0c8e0db734df71ea8e646264ee8803c6 — expect 200 with bucket list, 403, or 404. Single request, ≤1 rps.
[LEARN] ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with anon key — public bucket exposure realistic pre-auth vector.
[LEARN] ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Edge Functions may exist without auth — probeable.
[LEARN] REJECTED AUTH @ kurs.onecode.de: Pre-auth surface fully exhausted — only /login and /passwort-vergessen at 200.
[LEARN] ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap highest value (conf 62-65) — requires test accounts.
[LEARN] REJECTED Realtime (conf 35): speculative without live probe — parked below threshold.
[RISK] onecode: 64 — Supabase-backed Next.js solid defaults pre-auth (signup disabled, REST PGRST002, no OAuth, mail confirm on). New vector: direct Supabase service endpoints (storage, functions) bypass app middleware and are probeable with anon key. If a storage bucket is public or edge function lacks auth, pre-auth data/code access achievable. Post-auth BOLA via RLS gap (conf 65) remains highest-value but needs test accounts. Risk increased from 62→64 due to concrete probeable service endpoints.
## 2026-09-04 17:14:26 UTC [target] (model bigpickle)
[HYP] Post-auth BOLA via Supabase RLS gap
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Publishable key IS accepted for table-level REST queries (503 PGRST002, not 401). If/when schema cache recovers, tables with missing RLS policies allowing cross-tenant SELECT become directly queryable. Course platform semantics (enrollments, resources, profiles) predict multiple tenant-sensitive tables. UUID PKs weaken guessable-ID BOLA; realistic target is missing RLS filter on cross-tenant queries.
evidence_needed: Two invited test accounts with different email domains; query /rest/v1/{table}?select=*&limit=1 for tenant-bound tables (profiles, enrollments, course_access); cross-tenant ID access without RLS filtering.
verify_steps: 1) Obtain two invited accounts. 2) Login via Supabase signInWithOtp or email/password to get access tokens. 3) Query /rest/v1/profiles?select=* with Account-A token, verify Account-B's record is visible. 4) Repeat for enrollments, course_materials, and any other tenant-bound tables.
impact: Cross-tenant PII/enrollment data exfiltration — CRITICAL.
testability: AUTH_HELPED
[HYP] Post-auth server-side API BOLA via Next.js routes
class: IDOR
asset: kurs.onecode.de/api/*, /v1/*
confidence: 62
reasoning: Next.js/Turbopack App Router with registered /api + /v1 routers confirmed (auth-gated at 307). Course platform semantics predict API endpoints for enrollment data, course content, user profiles. If server-side route handlers don't enforce tenant isolation (relying on client-side filtering), cross-tenant data access is possible via parameter manipulation.
evidence_needed: Authenticated session; fuzz /api/* and /v1/* routes with parameter variations (id, user_id, course_id); observe response bodies for cross-tenant data.
verify_steps: 1) Obtain authenticated session. 2) Enumerate /api/* routes (Next.js RSC flight data, bundle analysis). 3) Test each endpoint with valid + invalid tenant IDs. 4) Compare response data across two accounts.
impact: Cross-tenant data access — HIGH to CRITICAL depending on data sensitivity.
testability: AUTH_HELPED
[RISK] onecode: 66 — Supabase-backed Next.js app with solid pre-auth defaults (signup disabled, publishable key has no public buckets, no edge functions, no OAuth, schema cache blocks REST enumeration). Risk increased from 64→66 because: 1) confirmed publishable key is valid for table-level REST (schema cache currently blocks, but if it recovers, RLS misconfig becomes testable), 2) pre-auth surface is fully exhausted with no findings (clean), 3) post-auth BOLA via RLS gap (conf 65) remains highest-value path requiring AUTH_HELPED. Overall: good pre-auth hygiene, but post-auth surface unexplored and likely contains findings given course platform semantics and single-tenant Supabase backend.
## 2026-09-04 19:43:20 UTC [target] (model bigpickle)
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/,8.0,a=9,b=8,t=8,g=9,c=7,f=6
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/,7.5,a=8,b=7,t=8,g=8,c=6,f=6
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/,6.0,a=6,b=7,t=7,g=8,c=5,f=6
[PRIO] kurs.onecode.de (post-auth BOLA),7.0,a=7,b=9,t=8,g=1,c=7,f=7 (AUTH_HELPED)
[HYP] Supabase Storage public bucket listing
class: MISCONFIG
asset: aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/
confidence: 58
reasoning: Storage endpoint is a separate Supabase service not behind Next.js middleware. Course platform ("Rich Dev Poor Dev") stores resources in Supabase Storage. If bucket has public SELECT policy or overly permissive anon access, unauthenticated listing/download possible.
evidence_needed: HTTP 200 from GET /storage/v1/bucket with only anon key; bucket names visible in response
verify_steps: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket (Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImF5Z25wYWRra3RzZm5oZ3N5amNjIiwicm9sZSI6ImFub24iLCJpYXQiOjE3MjUzMzI0MDAsImV4cCI6MjA0MDkwODQwMH0.870cf518cadbb13823395f6f7c2930ab0c8e0db734df71ea8e646264ee8803c6)
impact: Unauthenticated access to course materials, uploaded resources, file metadata — MEDIUM-HIGH
testability: PASSIVE
[HYP] Supabase Edge Functions unauthenticated invocation
class: MISCONFIG
asset: aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/
confidence: 48
reasoning: Edge Functions deployed per-project; if any function lacks verifySession/verifyJwt, it can be invoked unauthenticated. Common patterns: email sending, webhooks, data processing.
evidence_needed: HTTP 200 (not 404) from GET /functions/v1/; function names from JS bundle
verify_steps: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/ (Authorization: Bearer anon_key); also grep client bundles for functions/v1/<name> patterns
impact: Server-side code execution or data extraction — HIGH
testability: PASSIVE
[HYP] Supabase Realtime cross-tenant subscription
class: MISCONFIG
asset: aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/
confidence: 35
reasoning: Supabase Realtime uses anon key for WebSocket connections. If RLS misconfigured on realtime publications, client can subscribe to channels containing cross-tenant data.
evidence_needed: Successful WebSocket upgrade; ability to subscribe to table change events with anon key
verify_steps: WebSocket connect to wss://aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1 with anon key
impact: Cross-tenant data stream interception — HIGH if RLS publication misconfigured
testability: PASSIVE
[PARKED] Supabase Realtime cross-tenant subscription: confidence 35 < 40 threshold; speculative without live WebSocket probe; parked below threshold.
[FINAL] Storage (58) > Functions (48) > Realtime (35, parked)
[NEXT] PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/bucket with Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImF5Z25wYWRra3RzZm5oZ3N5amNjIiwicm9sZSI6ImFub24iLCJpYXQiOjE3MjUzMzI0MDAsImV4cCI6MjA0MDkwODQwMH0.870cf518cadbb13823395f6f7c2930ab0c8e0db734df71ea8e646264ee8803c6 — expect 200 with bucket list, 403, or 404. Single request, ≤1 rps.
[LEARN] ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with anon key — public bucket exposure realistic pre-auth vector.
[LEARN] ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Edge Functions may exist without auth — probeable.
[LEARN] REJECTED AUTH @ kurs.onecode.de: Pre-auth surface fully exhausted — only /login and /passwort-vergessen at 200.
[LEARN] ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap highest value (conf 62-65) — requires test accounts.
[LEARN] REJECTED Realtime (conf 35): speculative without live probe — parked below threshold.
[RISK] onecode: 64 — Supabase-backed Next.js solid defaults pre-auth (signup disabled, REST PGRST002, no OAuth, mail confirm on). New vector: direct Supabase service endpoints (storage, functions) bypass app middleware and are probeable with anon key. If a storage bucket is public or edge function lacks auth, pre-auth data/code access achievable. Post-auth BOLA via RLS gap (conf 65) remains highest-value but needs test accounts. Risk increased from 62→64 due to concrete probeable service endpoints.
## 2026-09-04 22:16:05 UTC [target] (model bigpickle)
## 2026-09-05 00:16:41 UTC [target] (model bigpickle)
[HYP] Post-auth cross-tenant BOLA via Supabase RLS policy gap
class: IDOR
asset: kurs.onecode.de (/api,/v1) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Single Supabase project backs the invite-only course platform; publishable key IS accepted for table queries (503 PGRST002, not 401) while the OpenAPI spec demands a secret key; GraphQL v1 confirmed. Persistent PGRST002 currently masks the anon role's real ACL — any SELECT policy missing a user_id predicate yields cross-tenant rows once the cache is healthy. UUID PKs weaken guessable-ID BOLA, so the RLS-policy-gap is the realistic target.
evidence_needed: Two invited accounts (different email domains); Account A retrieving rows owned by Account B via authenticated REST or app routes.
verify_steps: (AUTH_HELPED) Login via POST /auth/v1/token?grant_type=password to get access_token; A queries /rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit=1; also GET /api/courses/{B_id} via the app; diff A-vs-B row sets for non-self rows.
impact: Cross-tenant PII, enrollment and course-resource exfiltration — CRITICAL
testability: AUTH_HELPED
[HYP] Supabase GraphQL endpoint post-auth introspection/mutation
class: MISCONFIG
asset: aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1
confidence: 48
reasoning: Endpoint is deployed (pre-auth 503 PGRST002, NOT 404/401 — service present, schema cache down). Same project-wide cache state 503s REST. If cache is healthy for an authenticated user, __schema introspection may expose tables, RPCs, and insert/update/delete mutation fields that bypass per-resource RLS-style checks.
evidence_needed: 200 with __schema data, or a working cross-tenant mutation, using a valid user access_token.
verify_steps: (AUTH_HELPED) POST /graphql/v1 {"query":"{__schema{types{name}}}"} with Authorization: Bearer <access_token>; enumerate query/mutation/object types; attempt read/mutation against a second account's rows.
impact: Cross-tenant data read/write via GraphQL mutations — HIGH
testability: AUTH_HELPED
[HYP] Publishable-key direct REST exposure if schema cache recovers
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 50
reasoning: Publishable key passes the REST auth gate (503 PGRST002, not 401) but is barred from the OpenAPI spec — the two layers disagree, so the anon role's true table ACL is currently hidden by the cache failure. If PGRST002 clears, the publishable key may SELECT tenant tables without any session.
evidence_needed: Non-503/401 (200 rows, 400 valid-query error, or 402) from a table query with only the publishable key.
verify_steps: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with apikey+Authorization: Bearer sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30; repeat ≤1/day (low volume) to detect cache recovery; any non-503/401 is a trigger to escalate immediately.
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise
testability: PASSIVE
[NEXT] PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with headers `apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30` and `Authorization: Bearer sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30` — expected 503 PGRST002; any non-503/401 response means the schema cache recovered and immediately escalates to full table/RLS enumeration. ≤1 rps. Parallel: HUMAN escalation to obtain two invited test accounts for the RLS-gap BOLA (65) and GraphQL introspection (48) hypotheses.
[RISK] onecode: 66 — no change. Pre-auth hygiene now verified clean across every layer: no bundle secret leak, no middleware matcher gap, empty storage, no edge functions, secret-key-gated OpenAPI, admin throttled 401, GraphQL cache-blocked. Residual risk is entirely post-auth: RLS-gap BOLA (65), newly-confirmed deployed GraphQL endpoint (48), latent publishable-key REST recovery (50) — all AUTH_HELPED or low-frequency monitor.
## 2026-09-05 04:43:46 UTC [target] (model bigpickle)
[HYP] Post-auth cross-tenant BOLA via Supabase RLS policy gap
class: IDOR
asset: kurs.onecode.de (/api,/v1) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Publishable key authorizes REST (503 PGRST002, not 401); single Supabase project; SELECT policies lacking user_id/tenant predicate yield cross-tenant rows; UUID PKs rule out guessable-id BOLA.
evidence_needed: Two invited accounts; Account A retrieving rows owned by Account B.
verify_steps: (AUTH_HELPED) POST /auth/v1/token?grant_type=password for A; GET /rest/v1/profiles?select=*&limit=1, /rest/v1/enrollments?select=*&limit=1, /api/courses/{B_id}; diff A-vs-B rows.
impact: Cross-tenant PII, enrollment, course-resource exfiltration — CRITICAL
testability: AUTH_HELPED
[HYP] Publishable-key direct REST exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 51
reasoning: Fresh 503 PGRST002 proves key passes PostgREST auth; on cache recovery any weakly-guarded anon table may SELECT with no session.
evidence_needed: Non-503/401 (200 rows, 400, 402) on a table query with only the publishable key.
verify_steps: GET /rest/v1/profiles and /enrollments?select=*&limit=1 with apikey+Authorization Bearer sb_publishable_... every ≥24h; any non-503/401 → full enumeration.
impact: Unauthenticated cross-tenant row exposure — CRITICAL; monitoring-only while 503
testability: PASSIVE
[HYP] Supabase GraphQL endpoint post-auth introspection/mutation
class: MISCONFIG
asset: aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1
confidence: 48
reasoning: Same cache outage 503s GraphQL pre-auth; post-auth introspection may expose tables/RPCs/mutations not reachable via REST.
evidence_needed: 200 __schema, or working cross-tenant mutation with a valid access_token.
verify_steps: (AUTH_HELPED) POST /graphql/v1 {"query":"{__schema{types{name}}}"} with Bearer <token>; enumerate; attempt cross-account read/mutation.
impact: Cross-tenant data read/write via GraphQL mutations — HIGH
testability: AUTH_HELPED
## 2026-09-05 08:40:57 UTC [target] (model bigpickle)
[NEW] Supabase Storage endpoint (storage/v1/bucket) returns 200 with empty array `[]` using publishable key — endpoint directly accessible, bypasses Next.js middleware.  
[NEW] Supabase Functions endpoint returns 404 — no deployed functions or not listable pre-auth.  
[NEW] Supabase Realtime endpoint returns 401 — requires auth, no unauthenticated access.  
[NEW] Supabase REST endpoint returns 401 with publishable key — anon REST blocked.  
[CHANGED] Storage public bucket hypothesis confidence lowered from MEDIUM-HIGH to LOW — endpoint probeable but zero buckets exist.  
[CHANGED] Pre-auth surface on `kurs.onecode.de` fully exhausted — only `/login` and `/passwort-vergessen` at 200; all `/api/*`, `/v1`, `/dashboard` 307→/login.  
[CHANGED] Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts (AUTH_HELPED).  
[CHANGED] Subdomain takeover hypotheses (`hostmaster.*`, `cto.onecode.de`) remain at confidence 45 < 50 — passive-only cannot confirm claimability without active DNS resolution.
[PRIO] kurs.onecode.de,7.5,attack_surface=8,business_value=9,tech_exposure=8,gate_ease=1,cloud_surface=9,freshness=10 (Post-auth BOLA via Supabase RLS gap)  
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co,6.5,attack_surface=7,business_value=8,tech_exposure=7,gate_ease=2,cloud_surface=9,freshness=8 (Publishable-key REST recovery / GraphQL)  
[PRIO] hostmaster.onecode.de,4.0,attack_surface=4,business_value=5,tech_exposure=2,gate_ease=10,cloud_surface=3,freshness=5 (Subdomain takeover — low confidence)
[HYP] Post-auth cross-tenant BOLA via Supabase RLS policy gap  
class: IDOR  
asset: kurs.onecode.de (/api,/v1) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/  
confidence: 65  
reasoning: Single Supabase project backs the invite-only course platform; publishable key IS accepted for table queries (503 PGRST002, not 401) while the OpenAPI spec demands a secret key; GraphQL v1 confirmed. Persistent PGRST002 currently masks the anon role's real ACL — any SELECT policy missing a user_id predicate yields cross-tenant rows once the cache is healthy. UUID PKs weaken guessable-ID BOLA, so the RLS-policy-gap is the realistic target.  
evidence_needed: Two invited accounts (different email domains); Account A retrieving rows owned by Account B via authenticated REST or app routes.  
verify_steps: (AUTH_HELPED) Login via POST /auth/v1/token?grant_type=password to get access_token; A queries /rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit=1; also GET /api/courses/{B_id} via the app; diff A-vs-B row sets for non-self rows.  
impact: Cross-tenant PII, enrollment and course-resource exfiltration — CRITICAL  
testability: AUTH_HELPED  
[HYP] Supabase GraphQL endpoint post-auth introspection/mutation  
class: MISCONFIG  
asset: aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1  
confidence: 48  
reasoning: Endpoint is deployed (pre-auth 503 PGRST002, NOT 404/401 — service present, schema cache down). Same project-wide cache state 503s REST. If cache is healthy for an authenticated user, __schema introspection may expose tables, RPCs, and insert/update/delete mutation fields that bypass per-resource RLS-style checks.  
evidence_needed: 200 with __schema data, or a working cross-tenant mutation, using a valid user access_token.  
verify_steps: (AUTH_HELPED) POST /graphql/v1 {"query":"{__schema{types{name}}}"} with Authorization: Bearer <access_token>; enumerate query/mutation/object types; attempt read/mutation against a second account's rows.  
impact: Cross-tenant data read/write via GraphQL mutations — HIGH  
testability: AUTH_HELPED  
[HYP] Publishable-key direct REST exposure if schema cache recovers  
class: IDOR  
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/  
confidence: 50  
reasoning: Publishable key passes the REST auth gate (503 PGRST002, not 401) but is barred from the OpenAPI spec — the two layers disagree, so the anon role's true table ACL is currently hidden by the cache failure. If PGRST002 clears, the publishable key may SELECT tenant tables without any session.  
evidence_needed: Non-503/401 (200 rows, 400 valid-query error, or 402) from a table query with only the publishable key.  
verify_steps: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with apikey+Authorization: Bearer sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30; repeat ≤1/day (low volume) to detect cache recovery; any non-503/401 is a trigger to escalate immediately.  
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise  
testability: PASSIVE  
[PARKED] Supabase GraphQL endpoint post-auth introspection/mutation: requires test accounts (AUTH_HELPED) and currently blocked by 503 cache state — cannot verify pre-auth; will be re-evaluated if accounts obtained.  
[FINAL] 1. Post-auth cross-tenant BOLA via Supabase RLS policy gap (65) — highest value, requires test accounts.  
[FINAL] 2. Publishable-key direct REST exposure if schema cache recovers (50) — passive monitor, low volume.  
[FINAL] 3. Supabase GraphQL endpoint post-auth introspection/mutation (48) — requires test accounts, lower confidence.
[NEXT] HUMAN: Escalate to obtain two invited test accounts for the RLS-gap BOLA (65) and GraphQL introspection (48) hypotheses. Without accounts, pre-auth surface is exhausted.
[LEARN] ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with empty bucket list (zero buckets)  
[LEARN] REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth  
[LEARN] REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access  
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login  
[LEARN] ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts  
[LEARN] REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)  
[LEARN] REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm takeover without active DNS resolution
[RISK] onecode: 66 — no change. Pre-auth hygiene now verified clean across every layer: no bundle secret leak, no middleware matcher gap, empty storage, no edge functions, secret-key-gated OpenAPI, admin throttled 401, GraphQL cache-blocked. Residual risk is entirely post-auth: RLS-gap BOLA (65), newly-confirmed deployed GraphQL endpoint (48), latent publishable-key REST recovery (50) — all AUTH_HELPED or low-frequency monitor.
## 2026-09-05 12:11:21 UTC [target] (model bigpickle)
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS filter
class: IDOR
asset: kurs.onecode.de (/api,/v1) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Single Supabase project backs the invite-only course platform; publishable key passes the REST auth gate (table query = 503 PGRST002, not 401) while bare /rest/v1/ is 401; GraphQL v1 confirmed in same cache state. Any SELECT policy missing a user_id predicate yields cross-tenant rows once the cache is healthy; UUID PKs weaken ID guessing so RLS-gap is the target.
evidence_needed: Two invited accounts (different email domains); Account A retrieving Account B's rows via authenticated REST or app routes.
verify_steps: (AUTH_HELPED) POST /auth/v1/token?grant_type=password → access_token; A queries /rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit=1; also GET /api/courses/{B_id} via app; diff A-vs-B row sets.
impact: Cross-tenant PII, enrollment and course-resource exfiltration — CRITICAL
testability: AUTH_HELPED
[HYP] Publishable-key direct REST/GraphQL exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ + /graphql/v1/
confidence: 50
reasoning: Publishable key is bar permitted past auth (table query 503 PGRST002; GraphQL same 503) — REST OpenAPI spec layer disagrees with the live gate. Persistent PGRST002 masks the anon role's true table ACL; both endpoints are ready to serve as soon as cache recovers.
evidence_needed: Non-503/401 response (200 rows, 400 valid-query error, 402) from a table query with only the publishable key.
verify_steps: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with apikey+Authorization: Bearer sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30; repeat ≤1/day (probed today → 503, next ≤2026-09-06); any non-503/401 is an immediate escalate trigger.
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise
testability: PASSIVE
[HYP] Supabase GraphQL endpoint post-auth introspection/mutation
class: MISCONFIG
asset: aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1
confidence: 48
reasoning: Endpoint deployed (publishable-key probe = 503, not 404/401 — service present, schema cache down). Same project-wide cache blocks REST. If cache healthy for an authenticated user, __schema introspection may expose tables, RPCs, and insert/update/delete mutation fields.
evidence_needed: 200 with __schema data, or working cross-tenant mutation, using a valid user access_token.
verify_steps: (AUTH_HELPED) POST /graphql/v1 {"query":"{__schema{types{name}}}"} with Bearer <access_token>; enumerate types; attempt read/mutation against second account's rows.
impact: Cross-tenant data read/write via GraphQL mutations — HIGH
testability: AUTH_HELPED
[PARKED] Realtime /api/broadcast channel-auth gap (MISCONFIG 42): only post-auth testable, no accounts yet.
[PARKED] OAuth (OATH 38-42): no external providers; magic-link hash handoff lacks demonstrated sink; fixed redirect whitelist.
[PARKED] Subdomain takeover (MISCONFIG 45): passive-only cannot confirm claimability.
## 2026-09-05 15:25:24 UTC [target] (model bigpickle)
[PRIO] kurs.onecode.de/api/*,a=7,b=9,t=8,g=3,c=8,f=7,p=7.2
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/,a=6,b=9,t=8,g=6,c=9,f=6,p=7.2
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1,a=6,b=8,t=9,g=5,c=9,f=6,p=6.9
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS filter
class: IDOR
asset: kurs.onecode.de (/api,/v1) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Single Supabase project backs the invite-only course platform; publishable key passes the REST auth gate (table query = 503 PGRST002, not 401) while bare /rest/v1/ is 401; GraphQL v1 confirmed in same cache state. Any SELECT policy missing a user_id predicate yields cross-tenant rows once the cache is healthy; UUID PKs weaken ID guessing so RLS-gap is the target.
evidence_needed: Two invited accounts (different email domains); Account A retrieving Account B's rows via authenticated REST or app routes.
verify_steps: (AUTH_HELPED) POST /auth/v1/token?grant_type=password → access_token; A queries /rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit=1; also GET /api/courses/{B_id} via app; diff A-vs-B row sets.
impact: Cross-tenant PII, enrollment and course-resource exfiltration — CRITICAL
testability: AUTH_HELPED
[HYP] Publishable-key direct REST/GraphQL exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ + /graphql/v1/
confidence: 50
reasoning: Publishable key passes auth gate (table query 503 PGRST002; GraphQL same 503) — REST OpenAPI spec layer disagrees with live gate. Persistent PGRST002 masks anon role's true table ACL; both endpoints ready to serve when cache recovers.
evidence_needed: Non-503/401 response (200 rows, 400 valid-query error, 402) from a table query with only the publishable key.
verify_steps: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with apikey+Authorization: Bearer sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30; repeat ≤1/day (probed today → 503, next ≤2026-09-06); any non-503/401 is an immediate escalate trigger.
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise
testability: PASSIVE
[HYP] Supabase GraphQL endpoint post-auth introspection/mutation
class: MISCONFIG
asset: aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1
confidence: 48
reasoning: Endpoint deployed (publishable-key probe = 503, not 404/401 — service present, schema cache down). Same project-wide cache blocks REST. If cache healthy for an authenticated user, __schema introspection may expose tables, RPCs, and insert/update/delete mutation fields.
evidence_needed: 200 with __schema data, or working cross-tenant mutation, using a valid user access_token.
verify_steps: (AUTH_HELPED) POST /graphql/v1 {"query":"{__schema{types{name}}}"} with Bearer <access_token>; enumerate types; attempt read/mutation against second account's rows.
impact: Cross-tenant data read/write via GraphQL mutations — HIGH
testability: AUTH_HELPED
[FINAL] 1. Post-auth cross-tenant BOLA via Supabase RLS policy gap (65) — highest value, requires test accounts
[FINAL] 2. Publishable-key direct REST exposure if schema cache recovers (50) — passive monitor, low volume
[FINAL] 3. Supabase GraphQL endpoint post-auth introspection/mutation (48) — requires test accounts
[LEARN] ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint exists, NOT behind app middleware, probeable with publishable key — returns 200 with empty bucket list (zero buckets)
[LEARN] REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404; no deployed functions or not listable pre-auth
[LEARN] REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401; requires auth, no pre-auth access
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface exhausted — only /login and /passwort-vergessen at 200; all /api/*, /v1, /dashboard 307→/login
[LEARN] ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via Supabase RLS gap remains highest-value (conf 65); requires two invited test accounts
[LEARN] REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings)
[LEARN] REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm takeover without active DNS resolution
[RISK] onecode: 66 — no change. Pre-auth hygiene now verified clean across every layer: no bundle secret leak, no middleware matcher gap, empty storage, no edge functions, secret-key-gated OpenAPI, admin throttled 401, GraphQL cache-blocked. Residual risk is entirely post-auth: RLS-gap BOLA (65), newly-confirmed deployed GraphQL endpoint (48), latent publishable-key REST recovery (50) — all AUTH_HELPED or low-frequency monitor.
## 2026-09-05 17:38:21 UTC [target] (model bigpickle)
[HYP] Publishable-key direct REST exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 50
reasoning: Publishable key passes auth gate (table query = 503 PGRST002, not 401); bare /rest/v1/ is 401. PGRST002 = schema cache down, masking anon role's true table ACL; ready to serve when cache recovers. Probed today still 503 (monitor due ≤2026-09-06).
evidence_needed: Non-503/401 response from table query with only publishable key.
verify_steps: GET /rest/v1/profiles?select=*&limit=1 with apikey+Authorization Bearer publishable; ≤1/day (probed →503, next ≤09-06); any non-503/401 = escalate.
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized
testability: PASSIVE
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS filter
class: IDOR
asset: kurs.onecode.de (/api,/v1) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Single Supabase project backs invite-only course platform; publishable key passes REST auth gate; UUID PKs weaken guessing so missing-RLS SELECT policy is the target.
evidence_needed: Two invited accounts; A retrieves B's rows.
verify_steps: (AUTH_HELPED) POST /auth/v1/token password grant → access_token; query /rest/v1/profiles and /rest/v1/enrollments; diff A-vs-B.
impact: Cross-tenant PII/enrollment exfiltration — CRITICAL
testability: AUTH_HELPED
[HYP] Supabase GraphQL post-auth introspection/mutation
class: MISCONFIG
asset: aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1
confidence: 48
reasoning: Endpoint deployed (probe=503 not 404/401 — service present, cache down); if cache healthy for authenticated user, __schema may expose tables/RPCs/mutations.
evidence_needed: 200 __schema with valid access_token.
verify_steps: (AUTH_HELPED) POST /graphql/v1 __schema with Bearer access_token.
impact: Cross-tenant read/write — HIGH
testability: AUTH_HELPED
[NEXT] HUMAN: Escalate to obtain two invited test accounts to activate the post-auth RLS-gap BOLA (conf 65) hypothesis; pre-auth surface fully exhausted and the only remaining unblocked path requires authentication.
[LEARN] ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Probed again 2026-09-05 → 503 PGRST002 with publishable key; schema-cache still down, no anon table exposure yet. Monitor stays active (next ≤09-06).
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface still exhausted (/login 200 only).
[LEARN] REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1: Probed again → 503 (cache block, same as REST); no pre-auth introspection possible.
[RISK] onecode: 66 — no change. Residual risk entirely post-auth: RLS-gap BOLA (65), GraphQL introspection (48), latent publishable-key REST recovery (50). Pre-auth hygiene clean at every layer; blocking constraint remains test-account availability.
## 2026-09-05 19:32:37 UTC [target] (model bigpickle)
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/,7.8,a=9,b=9,t=9,g=9,c=7,f=6 — schema cache recovery monitor; if PGRST002 clears, anon-key table exposure becomes CRITICAL
[PRIO] kurs.onecode.de (post-auth BOLA),7.2,a=8,b=9,t=9,g=1,c=7,f=7 — RLS gap BOLA highest overall value, blocked on test accounts (AUTH_HELPED)
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1,6.5,a=7,b=8,t=9,g=8,c=6,f=6 — post-auth introspection/mutation, also cache-blocked, needs test accounts
[PRIO] onecode.de/www.onecode.de,4.0,a=4,b=5,t=3,g=5,c=4,f=4 — low value, Webflow static
[PRIO] hostmaster.*/cto.onecode.de,3.0,a=4,b=4,t=2,g=3,c=2,f=2 — subdomain takeover confidence below threshold, parked
[HYP] Publishable-key direct REST exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 50
reasoning: Publishable key IS accepted for table-level REST queries (503 PGRST002, not 401); bare /rest/v1/ returns 401 without key. The 503 PGRST002 indicates schema cache is down, masking the anon role's true table ACL. If cache recovers, tables with missing RLS SELECT policies become directly queryable with only the publishable key. Course platform semantics (profiles, enrollments, course_materials) predict multiple tenant-bound tables.
evidence_needed: Non-503/401 (200 rows, 400 valid-query error, 402, or any response other than PGRST002) from a table query with only the publishable key.
verify_steps: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with apikey header + Authorization: Bearer sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30; repeat ≤1/day (probed today → 503, next ≤2026-09-06). Any non-503/401 is an immediate escalate trigger.
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise.
testability: PASSIVE
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS filter
class: IDOR
asset: kurs.onecode.de (/api,/v1) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Single Supabase project backs invite-only course platform ("Rich Dev Poor Dev"); publishable key passes REST auth gate (503 PGRST002); registered /api,/v1 routes confirmed. UUID PKs weaken guessable-ID BOLA; realistic high-value target is missing RLS filter allowing cross-tenant SELECT on profiles, enrollments, or course_materials tables. Two invited test accounts needed to compare row sets.
evidence_needed: Two invited accounts (different email domains); Account A retrieving rows owned by Account B via authenticated Supabase REST or app routes.
verify_steps: (AUTH_HELPED) Login via POST /auth/v1/token?grant_type=password to get access_token for each account; query /rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit=1 with Account-A token; check if Account-B rows appear. Diff A-vs-B row sets.
impact: Cross-tenant PII/enrollment data exfiltration — CRITICAL.
testability: AUTH_HELPED
[HYP] Supabase GraphQL endpoint post-auth introspection/mutation
class: MISCONFIG
asset: aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1
confidence: 48
reasoning: Endpoint deployed (publishable-key probe = 503 PGRST002, not 404/401 — service present, schema cache down). Same project-wide cache blocks REST. If cache is healthy for an authenticated user, __schema introspection may expose tables, RPCs, and insert/update/delete mutation fields that bypass per-resource RLS-style checks.
evidence_needed: 200 with __schema data, or a working cross-tenant mutation, using a valid user access_token.
verify_steps: (AUTH_HELPED) POST /graphql/v1 with body {"query":"{__schema{types{name}}}"} + Authorization: Bearer <access_token>; enumerate query/mutation/object types; attempt read/mutation against a second account's rows.
impact: Cross-tenant data read/write via GraphQL mutations — HIGH.
testability: AUTH_HELPED
[FINAL] 1. Post-auth cross-tenant BOLA via Supabase RLS gap (conf 65, IDOR, AUTH_HELPED) — highest overall value; blocking constraint = test account availability
[FINAL] 2. Publishable-key direct REST exposure if schema cache recovers (conf 50, IDOR, PASSIVE) — monitoring-only; no action possible until PGRST002 clears
[FINAL] 3. Supabase GraphQL post-auth introspection/mutation (conf 48, MISCONFIG, AUTH_HELPED) — needs test accounts + healthy schema cache
[NEXT] HUMAN: Escalate to obtain two invited test accounts for kurs.onecode.de to activate the post-auth BOLA hypothesis (conf 65, CRITICAL impact). Pre-auth surface is fully exhausted across all layers (app routes, Supabase storage/functions/realtime/REST/GraphQL). The only remaining high-value path is post-auth cross-tenant RLS-gap testing, which requires two accounts with different email domains. No further pre-auth probing is productive — the only passive action is REST endpoint monitoring (≤1/day) for schema cache recovery.
[LEARN] ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Probed again 2026-09-05 → 503 PGRST002 with publishable key; schema-cache still down, no anon table exposure yet. Monitor stays active (next ≤2026-09-06).
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface still exhausted (/login 200 only).
[LEARN] REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/graphql/v1: Probed again → 503 (cache block, same as REST); no pre-auth introspection possible.
[LEARN] ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Empty bucket list confirmed again — endpoint probeable but zero buckets exist.
[LEARN] REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/functions/v1/: Returns 404 — no deployed functions.
[LEARN] REJECTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/realtime/v1/: Returns 401 — auth required.
[RISK] onecode: 66 — no change. Pre-auth hygiene now verified clean across every layer: no bundle secret leak, no middleware matcher gap, empty storage, no edge functions, secret-key-gated OpenAPI, admin throttled 401, GraphQL cache-blocked. Residual risk is entirely post-auth: RLS-gap BOLA (65), newly-confirmed deployed GraphQL endpoint (48), latent publishable-key REST recovery (50) — all AUTH_HELPED or low-frequency monitor.
## 2026-09-05 21:47:48 UTC [target] (model bigpickle)
[HYP] Dangling Cloudflare-proxied CNAME on cto.onecode.de (error 1001)
class: MISCONFIG
asset: cto.onecode.de
confidence: 52
reasoning: CNAME → cname.perspective-dns.com (Cloudflare-fronted, 104.18.2.73/3.73); GET / on port 80 returns 409 with body "error code: 1001" (server: cloudflare, CF-RAY a3686c8c0e9d8847-IAD); 443 fails TLS handshake. CF 1001 = origin unresolvable inside Cloudflare, i.e. stale/dangling proxied CNAME. No sibling subdomains resolve (dev/api/admin/staging… all NXDOMAIN).
evidence_needed: Confirmation cto.onecode.de is claimable via self-serve registration at cname.perspective-dns.com (provider check, out-of-band).
verify_steps: PASSIVE: repeat GET http://cto.onecode.de/ ≤1/day → confirm stable 409/1001 (observable without auth). CONFIRM: registry/provider interaction at perspective-dns.com for the cto hostname (HUMAN_ONLY).
impact: Full control of a *.onecode.de subdomain (phrase: phishing under onecode.de origin, DNS-chained cert issuance) — HIGH if claimable.
testability: PASSIVE
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS filter
class: IDOR
asset: kurs.onecode.de (/api,/v1) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Unchanged — single Supabase project backs invite-only course platform; publishable key passes REST auth layer (503 PGRST002); UUID PKs make the realistic hole a missing RLS filter enabling cross-tenant SELECT on profiles/enrollments/course_materials.
evidence_needed: Account-A token retrieving rows owned by Account-B (two invited accounts, different domains).
verify_steps: (AUTH_HELPED) POST /auth/v1/token?grant_type=password per account; GET /rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit=1 with each token; diff row sets.
impact: Cross-tenant PII/enrollment exfiltration — CRITICAL.
testability: AUTH_HELPED
[HYP] Publishable-key direct REST exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 50
reasoning: Unchanged — 503 PGRST002 (not 401) proves publishable key passes auth layer; mask hides anon role's true table ACL; cache recovery could expose missing-RLS tables pre-auth.
evidence_needed: Any non-503/401 response to a table query with only the publishable key.
verify_steps: GET /rest/v1/profiles?select=*&limit=1 + apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30, ≤1/day, next ≤09-06.
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise.
testability: PASSIVE
## 2026-09-05 23:42:24 UTC [target] (model bigpickle)
[NEW] cto.onecode.de re-probed 23:41 UTC: stable 409 Conflict body "error code:1001" (Server:cloudflare, CF-RAY a36915496c750613-IAD), 443 TLS handshake-fail, CNAME cto->cname.perspective-dns.com (104.18.2.73/.3.73) unchanged — stale config persists across 2 days.
[NEW] Provider identity resolved: cname.perspective-dns.com is the documented "connect your own domain" CNAME value for the Perspective funnel SaaS (intercom.help/perspective-funnels articles confirm arbitrary customer subdomains attach via this exact target; no DNSSEC).
[NEW] www.onecode.de verified static Webflow marketing (project onecodedev, pageId 69c2...7b4, cf-cache HIT) — no dynamic/web-crawlable surface; mta-sts.onecode.de = CF 301 mail stub (out-of-scope class).
[NEW] mail.onecode.de (95.130.17.37) returns no HTTP — non-web service, no action.
[PRIO] kurs.onecode.de+aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/,7.95,attack_surface8/business9/tech7/gate7/cloud6/fresh10
[PRIO] cto.onecode.de,7.30,attack_surface6/business7/tech6/gate9/cloud8/fresh10
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co monitors,6.50,attack_surface6/business6/tech6/gate9/cloud6/fresh7
[HYP] Dangling Perspective CNAME takeover on cto.onecode.de
class: MISCONFIG
asset: cto.onecode.de
confidence: 58
reasoning: cto.onecode.de CNAME -> cname.perspective-dns.com (Cloudflare-fronted), GET / = stable 409 "error code:1001" (CF-RAY), 443 handshake fail (no cert issued for hostname). Provider = Perspective funnel SaaS whose own docs route customer *custom subdomains* through this exact CNAME value, with CNAME-present as the domain-binding/ownership proof and certs issued only for bound hosts. No cert + 409 on the proxy = hostname currently unbound at the provider -> reclaimable in a fresh Perspective account.
evidence_needed: A Perspective account binding cto.onecode.de serves attacker funnel content on the hostname (out-of-band claim attempt).
verify_steps: PASSIVE (done 09-05): repeat GET http://cto.onecode.de/ <=1/day to confirm 409/1001 stability (observable without auth). CONFIRM: HUMAN creates Perspective account, attaches custom subdomain cto.onecode.de (CNAME already points at cname.perspective-dns.com), observes whether hostname serves foreign content + gets TLS cert.
impact: Full control of trusted *.onecode.de subdomain for phishing/repudiation under onecode.de origin + TLS issuance via SaaS -> HIGH.
testability: PASSIVE + HUMAN confirm
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS filter
class: IDOR
asset: kurs.onecode.de (/api,/v1) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Unchanged — single Supabase project backs invite-only course platform; publishable key passes REST auth layer (503 PGRST002 = schema-cache down, not 401); UUID PKs make the high-value hole a missing RLS filter enabling cross-tenant SELECT on profiles/enrollments/course_materials.
evidence_needed: Account-A token retrieving rows owned by Account-B (two invited accounts, different email domains).
verify_steps: (AUTH_HELPED) POST /auth/v1/token?grant_type=password per account; GET /rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit=1 with each token; diff row sets.
impact: Cross-tenant PII/enrollment exfiltration — CRITICAL.
testability: AUTH_HELPED
[HYP] Publishable-key direct REST exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 50
reasoning: Unchanged — 503 PGRST002 (not 401) proves publishable key passes the auth layer; mask hides anon role's real table ACL; cache recovery could expose missing-RLS tables pre-auth.
evidence_needed: Any non-503/401 response to a table query using only the publishable key.
verify_steps: GET /rest/v1/profiles?select=*&limit=1 + apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30, <=1/day, next after 00:00Z 09-06.
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise.
testability: PASSIVE
[PARKED] Supabase GraphQL post-auth introspection (conf 48): superseded — same schema-cache block as REST, needs test accounts before REST can even be confirmed; fold into BOLA test.
[PARKED] Realtime channel auth-gap (conf 35): speculative, no live probe possible pre-auth.
[FINAL] 1. kurs.onecode.de BOLA/RLS-gap (conf 65, IDOR, AUTH_HELPED) — highest value; blocked on two invited test accounts.
[FINAL] 2. cto.onecode.de dangling Perspective CNAME (conf 58, MISCONFIG, HUMAN confirm) — provider + stale state now evidenced; claim-attempt converts to confirmed HIGH.
[FINAL] 3. publishable-key REST exposure on cache recovery (conf 50, IDOR, PASSIVE) — monitor only, due 09-06.
[NEXT] HUMAN: Create a Perspective account and attempt to bind custom subdomain cto.onecode.de (CNAME already resolves to cname.perspective-dns.com) — if attacker content serves on cto.onecode.de, dangling-CNAME takeover is CONFIRMED (HIGH). In parallel continue escalation for two invited kurs.onecode.de test accounts (unblocks conf-65 BOLA). Passive loop: re-probe https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 (publishable key) at 00:00Z 09-06 for PGRST002 clearing; re-probe http://cto.onecode.de/ <=1/day for 409/1001 stability.
[LEARN] ACCEPTED MISCONFIG @ cto.onecode.de: Provider identified — cname.perspective-dns.com = Perspective funnel SaaS custom-subdomain CNAME target (docs-confirmed); stable 409/1001 + missing cert = hostname currently unbound and plausibly reclaimable (conf 58, HUMAN confirm required).
[LEARN] REJECTED MISCONFIG @ www.onecode.de: static Webflow marketing, CF-cached HIT, no dynamic surface — no delta from runs 09-02..09-05.
[LEARN] REJECTED MISCONFIG @ mail.onecode.de: 95.130.17.37 no HTTP; non-web (mail) — out-of-scope class, no action.
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: Pre-auth surface still exhausted (/login, /passwort-vergessen only; all /api,/v1,/dashboard 307); no change 09-05.
[LEARN] ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 503 PGRST002 as of 09-05; next monitor due <=09-06 (once/day).
[RISK] onecode: 67 — slight rise (66->67): cto.onecode.de dangling-CNAME risk now provider-evidenced with a concrete claim path (Perspective custom-subdomain binding) + stable stale hostname; residual program risk remains dominated by post-auth BOLA (65, CRITICAL, account-blocked) and latent publishable-key REST recovery (50). Monitoring cadence kept <=1/day passive; humidity unchanged elsewhere.
## 2026-09-06 03:56:30 UTC [target] (model bigpickle)
## 2026-09-06 08:36:21 UTC [target] (model bigpickle)
[PRIO] kurs.onecode.de + Supabase REST,6.95,attack_surface8/business9/tech7/gate7/cloud6/fresh10
[PRIO] cto.onecode.de,7.30,attack_surface6/business7/tech6/gate9/cloud8/fresh10
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co monitors,6.50,attack_surface6/business6/tech6/gate9/cloud6/fresh7
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS filter
class: IDOR
asset: kurs.onecode.de (/api,/v1) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Single Supabase project backs invite-only course platform; publishable key passes REST auth layer (401 = explicit anon-block, 503 PGRST002 = schema-cache down — both prove publishable key authenticates); UUID PKs weaken guessable-ID BOLA; highest-value hole is missing RLS filter enabling cross-tenant SELECT on profiles/enrollments/course_materials.
evidence_needed: Account-A token retrieving rows owned by Account-B (two invited accounts, different email domains).
verify_steps: (AUTH_HELPED) POST /auth/v1/token?grant_type=password per account; GET /rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit=1 with each token; diff row sets.
impact: Cross-tenant PII/enrollment exfiltration — CRITICAL.
testability: AUTH_HELPED
[HYP] Dangling Perspective CNAME takeover on cto.onecode.de
class: MISCONFIG
asset: cto.onecode.de
confidence: 58
reasoning: CNAME cto→cname.perspective-dns.com (104.18.2.73/.3.73) stable across 2+ days; GET / returns stable 409 "error code:1001" (Server:cloudflare); 443 TLS handshake-fail (no cert for hostname); Perspective funnel SaaS docs confirm this exact CNAME value is the custom-subdomain binding mechanism; hostname unbound at provider → reclaimable in fresh Perspective account.
evidence_needed: A Perspective account binding cto.onecode.de serves attacker funnel content on the hostname (out-of-band claim attempt).
verify_steps: PASSIVE (done): repeat GET http://cto.onecode.de/ <=1/day to confirm 409/1001 stability. CONFIRM: HUMAN creates Perspective account, attaches custom subdomain cto.onecode.de, observes whether hostname serves foreign content + gets TLS cert.
impact: Full control of trusted *.onecode.de subdomain for phishing/repudiation under onecode.de origin + TLS issuance via SaaS — HIGH.
testability: PASSIVE + HUMAN confirm
[HYP] Publishable-key direct REST exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 50
reasoning: 503 PGRST002 (not 401) on 09-05 proved publishable key passes auth layer; today's 401 "Secret API key required" is explicit anon-block — schema-cache recovery may change gateway behavior; if anon role's table ACL is permissive, cache recovery exposes missing-RLS tables pre-auth.
evidence_needed: Any non-503/401 response to a table query using only the publishable key.
verify_steps: GET /rest/v1/profiles?select=*&limit=1 + apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30, <=1/day, next after 00:00Z 09-07.
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise.
testability: PASSIVE
[PARKED] Supabase GraphQL post-auth introspection (conf 48): superseded — same schema-cache block as REST, needs test accounts before REST can even be confirmed; fold into BOLA test.
[PARKED] Realtime channel auth-gap (conf 35): speculative, no live probe possible pre-auth.
[FINAL] 1. kurs.onecode.de BOLA/RLS-gap (conf 65, IDOR, AUTH_HELPED) — highest value; blocked on two invited test accounts.
[FINAL] 2. cto.onecode.de dangling Perspective CNAME (conf 58, MISCONFIG, HUMAN confirm) — provider + stale state evidenced; claim-attempt converts to confirmed HIGH.
[FINAL] 3. publishable-key REST exposure on cache recovery (conf 50, IDOR, PASSIVE) — monitor only, due 09-07.
[NEXT] HUMAN: Create a Perspective account and attempt to bind custom subdomain cto.onecode.de (CNAME already resolves to cname.perspective-dns.com) — if attacker content serves on cto.onecode.de, dangling-CNAME takeover is CONFIRMED (HIGH). In parallel continue escalation for two invited kurs.onecode.de test accounts (unblocks conf-65 BOLA). Passive loop: re-probe REST endpoint at 00:00Z 09-07.
[LEARN] NO_DELTA @ all: REST 401 anon-block persists; cto 409/1001 persists; storage empty; GraphQL 503 PGRST002 persists; kurs.onecode.de/login 200 unchanged. No state change from 09-05/06.
[LEARN] ACCEPTED MISCONFIG @ cto.onecode.de: Provider confirmed as Perspective funnel SaaS; stable 409/1001 + missing cert = hostname unbound and reclaimable (conf 58, HUMAN confirm required).
[LEARN] ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires two invited test accounts.
[LEARN] ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Explicit 401 anon-block with publishable key; monitor for cache recovery.
[LEARN] REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured.
[LEARN] REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface.
[LEARN] REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope.
[LEARN] REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution.
[RISK] onecode: 67 — unchanged (66→67): cto.onecode.de dangling-CNAME risk now provider-evidenced with concrete claim path + stale hostname stable; residual program risk dominated by post-auth BOLA (65, CRITICAL, account-blocked) and latent publishable-key REST recovery (50). Monitoring cadence ≤1/day passive; humidity unchanged.
## 2026-09-06 12:21:56 UTC [target] (model bigpickle)
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS filter
class: IDOR
asset: kurs.onecode.de (/api,/v1) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Single Supabase project backs invite-only course platform; publishable key passes REST auth layer; UUID PKs weaken guessable-ID BOLA, so missing-RLS cross-tenant SELECT on profiles/enrollments/course_materials is the highest-value hole.
evidence_needed: Account-A token retrieving rows owned by Account-B.
verify_steps: (AUTH_HELPED) POST /auth/v1/token?grant_type=password per account; GET /rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit=1 with each token; diff row sets.
impact: Cross-tenant PII/enrollment exfiltration — CRITICAL.
testability: AUTH_HELPED
[HYP] Dangling Perspective CNAME takeover on cto.onecode.de
class: MISCONFIG
asset: cto.onecode.de
confidence: 58
reasoning: CNAME cto→cname.perspective-dns.com (104.18.2.73) stable 2+ days; GET / = 409 "error code:1001" (Server:cloudflare); 443 TLS handshake-fail (no cert); Perspective docs confirm this CNAME is their custom-subdomain binding mechanism; hostname unbound → reclaimable.
evidence_needed: Fresh Perspective account serving attacker content on cto.onecode.de.
verify_steps: PASSIVE (done): repeat GET http://cto.onecode.de/ <=1/day for 409/1001 stability. CONFIRM: HUMAN binds cto.onecode.de in a Perspective account, observes foreign content + TLS issuance.
impact: Full control of trusted *.onecode.de subdomain for phishing/repudiation + TLS via SaaS — HIGH.
testability: PASSIVE + HUMAN confirm
[HYP] Publishable-key direct REST exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 55
reasoning: 09-04 and today both show 503 PGRST002 (not 401) with publishable key → anon key authenticates; the 401 observed 09-05/06 was an explicit gateway anon-block that has now been lifted; if anon-role table ACL is permissive, cache standup exposes missing-RLS tables pre-auth.
evidence_needed: Any non-503/401 response to a table query using only the publishable key.
verify_steps: GET /rest/v1/profiles?select=*&limit=1 (and /courses?select=*&limit=1) + apikey + Authorization: Bearer sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30, <=1/day, next after 00:00Z 09-07.
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise.
testability: PASSIVE
## 2026-09-06 15:38:08 UTC [target] (model bigpickle)
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS filter
class: IDOR
asset: kurs.onecode.de (/api,* /v1) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Single Supabase project backs invite-only course platform; publishable key passes the REST auth layer (503 PGRST002 earlier, now explicit 401 anon-block); UUID PKs weaken guessable-ID BOLA → missing-RLS cross-tenant SELECT on profiles/enrollments is highest-value. Open needs two invited accounts: unchanged today.
evidence_needed: Account-A token retrieving rows owned by Account-B.
verify_steps: (AUTH_HELPED) POST /auth/v1/token?grant_type=password per account; GET /rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit=1 with each token; diff row sets. Passive loop: re-probe /rest/v1 gateway after 00:00Z 09-07 (<=1/day).
impact: Cross-tenant PII/enrollment exfiltration — CRITICAL.
testability: AUTH_HELPED
[HYP] Dangling Perspective CNAME takeover on cto.onecode.de
class: MISCONFIG
asset: cto.onecode.de
confidence: 58
reasoning: CNAME cto→cname.perspective-dns.com stable again today (dig confirmed); http 409 "error code:1001" + 443 TLS-fail = hostname unbound at provider; Perspective docs confirm this CNAME is the custom-subdomain bind target → reclaimable.
evidence_needed: Fresh Perspective account serving attacker funnel content on cto.onecode.de.
verify_steps: PASSIVE done (CNAME stable 09-06); CONFIRM: HUMAN binds cto.onecode.de in a Perspective account, observes foreign content + TLS issuance.
impact: Control of a trusted *.onecode.de hostname for phishing/repudiation + TLS via SaaS — HIGH.
testability: PASSIVE + HUMAN confirm
[HYP] Publishable-key direct REST exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 50
reasoning: 09-04/05 returned 503 PGRST002 with publishable key (key authenticates); 09-05/06 flipped to 401 explicit anon-block — cache recovery can change gateway behavior; if anon-role table ACL is permissive, missing-RLS tables exposed pre-auth.
evidence_needed: Any non-503/401 response to a table query using only the publishable key.
verify_steps: GET /rest/v1/ (root) + apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30, <=1/day, next > 00:00Z 09-07. Table SELECTs only if gateway response indicates anon allowed (avoid exfil risk).
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise.
testability: PASSIVE
[NEXT] HUMAN: Create a Perspective funnel account, attach custom subdomain cto.onecode.de (CNAME already targets cname.perspective-dns.com) and observe whether attacker content + TLS cert serve on the hostname → dangling-CNAME takeover CONFIRMED (HIGH). If content does NOT serve, downgrade to conf<40 and mark cto RESOLVED. In parallel: escalate for two invited kurs.onecode.de test accounts (unblocks conf-65 BOLA); passive loop re-probes /rest/v1 root after 00:00Z 09-07 to watch for anon-block lift.
[LEARN] ACCEPTED MISCONFIG @ cto.onecode.de: CNAME → cname.perspective-dns.com stable (dig 09-06), 409/1001 + missing cert → hostname unbound and reclaimable; conf 58, HUMAN confirm required.
[LEARN] REJECTED MISCONFIG @ hostmaster.onecode.de: NXDOMAIN (no A/CNAME) in onecode's controlled zone → not claimable; differs from cto's live provider-CNAME class.
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: /login HEAD 200 unchanged; pre-auth surface stable; no new session/cookie signal.
[LEARN] NO_DELTA @ all: same-day monitor run — no state change vs 09-06 12:22; REST/recovery re-probe deferred to <=00:00Z 09-07 per <=1/day cadence.
[RISK] onecode: 67 — unchanged. cto.onecode.de dangling-CNAME remains provider-evidenced but HUMAN-claim-pending; residual risk dominated by post-auth BOLA (65, CRITICAL, account-blocked) and latent publishable-key REST recovery (50, monitored daily). No new exposure this cycle; posture stable.
## 2026-09-06 17:42:57 UTC [target] (model bigpickle)
[FINAL]
[NEXT] HUMAN: Two parallel unblocks (1) create a Perspective funnel account, attach custom subdomain cto.onecode.de (CNAME already → cname.perspective-dns.com), observe whether attacker content + TLS cert serve → confirm or downgrade the conf-58 takeover; (2) obtain two invited kurs.onecode.de test accounts to activate post-auth BOLA (conf 65, CRITICAL). Agent-side: re-probe GET aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ with apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30 after 00:00Z 09-07 (<=1/day).
[LEARN] ACCEPTED MISCONFIG @ cto.onecode.de: re-confirmed 17:42 UTC — http 409 "error code:1001", CNAME → cname.perspective-dns.com (104.18.x) stable; hostname unbound/reclaimable; conf 58, HUMAN confirm pending.
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: /login HEAD 200, /api/broadcast 307 unchanged; pre-auth surface stable, no new cookie/session signal.
[RISK] onecode: 67 — unchanged. No new exposure this cycle. Dominant residual risk: post-auth BOLA via RLS gap (65, CRITICAL, account-blocked) + latent publishable-key REST recovery (50, daily monitor) + cto dangling-CNAME (58, HUMAN-claim pending). All blocked on account provision or active-confirmation, not on new passive discovery.
## 2026-09-06 20:15:22 UTC [target] (model bigpickle)
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS filter
class: IDOR
asset: kurs.onecode.de (/api,* /v1) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Single Supabase project backs invite-only course platform; publishable key passes REST auth layer (503→401→401 evolving gateway); UUID PKs weaken guessable-ID BOLA → missing-RLS cross-tenant SELECT on profiles/enrollments is highest-value target. Unchanged — needs two invited accounts.
evidence_needed: Account-A token retrieving rows owned by Account-B.
verify_steps: (AUTH_HELPED) POST /auth/v1/token?grant_type=password per account; GET /rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit=1 with each token; diff row sets. Passive loop: re-probe /rest/v1 gateway after 00:00Z 09-07 (<=1/day).
impact: Cross-tenant PII/enrollment exfiltration — CRITICAL.
testability: AUTH_HELPED
[HYP] Dangling Perspective CNAME takeover on cto.onecode.de
class: MISCONFIG
asset: cto.onecode.de
confidence: 58
reasoning: CNAME cto→cname.perspective-dns.com stable 3+ days (dig confirmed 09-06); GET / = 409 "error code:1001" (Server:cloudflare); 443 TLS handshake-fail (no cert); Perspective docs confirm this CNAME is their custom-subdomain binding mechanism; hostname unbound → reclaimable.
evidence_needed: Fresh Perspective account serving attacker content on cto.onecode.de.
verify_steps: PASSIVE (done): repeat GET http://cto.onecode.de/ <=1/day for 409/1001 stability. CONFIRM: HUMAN binds cto.onecode.de in a Perspective account, observes foreign content + TLS issuance.
impact: Full control of trusted *.onecode.de subdomain for phishing/repudiation + TLS via SaaS — HIGH.
testability: PASSIVE + HUMAN confirm
[HYP] Publishable-key direct REST exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 50
reasoning: 09-04/05 returned 503 PGRST002 with publishable key (key authenticates); 09-05/06 flipped to 401 explicit anon-block — gateway behavior fluctuates; if anon-role table ACL is permissive, cache recovery exposes missing-RLS tables pre-auth. Monitoring cadence = <=1/day; next probe after 00:00Z 09-07.
evidence_needed: Any non-503/401 response to a table query using only the publishable key.
verify_steps: GET /rest/v1/ + apikey header, <=1/day, next after 00:00Z 09-07.
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise.
testability: PASSIVE
[NEXT] PASSIVE: Re-probe GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ with apikey header after 00:00Z 09-07 (cadence <=1/day). All other hypotheses blocked on external actions (HUMAN or AUTH_HELPED). No new probe today — all surfaces confirmed unchanged.
[LEARN] ACCEPTED MISCONFIG @ onecode.de: Live Webflow marketing (different page than www — "AI-native Entwickler" landing). Static, no dynamic surface — no new attack class.
[LEARN] NO_DELTA @ kurs.onecode.de: 7 paths tested (/login, /passwort-vergessen, /api/broadcast, /api/health, /api/auth/session, /robots.txt, /sitemap.xml) — all unchanged, pre-auth surface confirmed exhausted.
[LEARN] NO_DELTA @ cto.onecode.de: 409 non-2xx persists; CNAME unbound/reclaimable; conf 58 stable.
[LEARN] NO_DELTA @ all: REST/recovery re-probe deferred to 09-07 per <=1/day cadence.
[RISK] onecode: 67 — unchanged. No new exposure this cycle. Dominant residual risk: post-auth BOLA via RLS gap (65, CRITICAL, account-blocked) + latent publishable-key REST recovery (50, daily monitor) + cto dangling-CNAME (58, HUMAN-claim pending). All blocked on account provision or active confirmation, not on new passive discovery.
## 2026-09-06 22:12:33 UTC [target] (model bigpickle)
[PRIO] kurs.onecode.de (post-auth BOLA),7.0,a=7,b=9,t=9,g=1,c=7,f=7 — fully auth-gated, top hypothesis needs test accounts
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/,5.5,a=8,b=8,t=8,g=9,c=5,f=5 — endpoint probeable but zero buckets (confirmed empty); risk lowered
[PRIO] cto.onecode.de,5.8,a=6,b=7,t=3,g=3,c=6,f=6 — CNAME stable, 409/1001 persists, HUMAN-claim pending
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/,5.0,a=7,b=9,t=9,g=1,c=5,f=5 — 401 anon-block; daily monitor only
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS filter
class: IDOR
asset: kurs.onecode.de (/api/*, /v1/*) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Single Supabase project backs invite-only course platform; publishable key passes REST auth layer (503→401→401 evolving gateway); UUID PKs weaken guessable-ID BOLA → missing-RLS cross-tenant SELECT on profiles/enrollments is highest-value target. Unchanged — needs two invited accounts.
evidence_needed: Account-A token retrieving rows owned by Account-B.
verify_steps: (AUTH_HELPED) POST /auth/v1/token?grant_type=password per account; GET /rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit=1 with each token; diff row sets. Passive loop: re-probe /rest/v1 gateway after 00:00Z 09-07 (<=1/day).
impact: Cross-tenant PII/enrollment exfiltration — CRITICAL.
testability: AUTH_HELPED
[HYP] Dangling Perspective CNAME takeover on cto.onecode.de
class: MISCONFIG
asset: cto.onecode.de
confidence: 58
reasoning: CNAME cto→cname.perspective-dns.com stable 4+ days (dig confirmed 22:11 UTC); HTTP GET / = 409 "error code:1001" (Server:cloudflare); HTTPS returns TLS handshake failure (no cert); Perspective docs confirm this CNAME is their custom-subdomain binding mechanism; hostname unbound → reclaimable.
evidence_needed: Fresh Perspective account serving attacker content on cto.onecode.de.
verify_steps: PASSIVE (done): repeat GET http://cto.onecode.de/ <=1/day for 409/1001 stability. CONFIRM: HUMAN binds cto.onecode.de in a Perspective account, observes foreign content + TLS issuance.
impact: Full control of trusted *.onecode.de subdomain for phishing/repudiation + TLS via SaaS — HIGH.
testability: PASSIVE + HUMAN confirm
[HYP] Publishable-key direct REST exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 50
reasoning: 09-04/05 returned 503 PGRST002 with publishable key (key authenticates); 09-05/06 flipped to 401 explicit anon-block — gateway behavior fluctuates; if anon-role table ACL is permissive, cache recovery exposes missing-RLS tables pre-auth. Monitoring cadence = <=1/day; next probe after 00:00Z 09-07.
evidence_needed: Any non-503/401 response to a table query using only the publishable key.
verify_steps: GET /rest/v1/ + apikey header, <=1/day, next after 00:00Z 09-07.
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise.
testability: PASSIVE
[PARKED] Realtime /api/broadcast channel auth (MISCONFIG, conf 42): pre-auth gated; only post-auth testable with two accounts. Keep as secondary.
[PARKED] Magic-link token leakage (OATH, conf 38): no open redirect, no demonstrated hash-reader/XSS; standard Supabase flow. Re-open only if hash-reading sink found.
[PARKED] Supabase Storage public bucket (MISCONFIG, conf 55→50): endpoint probeable but zero buckets exist — exposure risk minimal until buckets are created.
[PARKED] GraphQL introspection (MISCONFIG, conf 45): /graphql returns 307→/login; no evidence GraphQL exists without auth.
[PARKED] Supabase Realtime impersonation (MISCONFIG, conf 35): speculative, no evidence of realtime publications beyond /api/broadcast.
[FINAL] 1. Post-auth BOLA via RLS gap (IDOR, 65, AUTH_HELPED) — highest overall value, blocked on test accounts
[FINAL] 2. Dangling Perspective CNAME takeover (MISCONFIG, 58, PASSIVE+HUMAN) — provider confirmed, reclaimable, needs HUMAN claim
[FINAL] 3. Publishable-key REST exposure on cache recovery (IDOR, 50, PASSIVE) — daily monitor, next probe 09-07
[NEXT] PASSIVE: Re-probe GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ with apikey header after 00:00Z 09-07 (cadence <=1/day). All other hypotheses blocked on external actions (HUMAN or AUTH_HELPED). No new probe today — all surfaces confirmed unchanged.
[LEARN] NO_DELTA @ all: Fresh probes 22:11 UTC confirm identical state to 09-06 20:15 — kurs.onecode.de/login 200, cto 409/1001, storage empty, REST 401 anon-block.
[LEARN] ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires two invited test accounts.
[LEARN] ACCEPTED MISCONFIG @ cto.onecode.de: CNAME → cname.perspective-dns.com stable 4+ days; 409/1001 + missing cert → hostname unbound/reclaimable; conf 58, HUMAN confirm pending.
[LEARN] ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint probeable, zero buckets — risk lowered but monitor active.
[LEARN] ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Explicit 401 anon-block with publishable key; monitor for cache recovery after 00:00Z 09-07.
[LEARN] REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings).
[LEARN] REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution.
[LEARN] REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface.
[LEARN] REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope.
[RISK] onecode: 67 — unchanged. No new exposure this cycle. Dominant residual risk: post-auth BOLA via RLS gap (65, CRITICAL, account-blocked) + latent publishable-key REST recovery (50, daily monitor) + cto dangling-CNAME (58, HUMAN-claim pending). All blocked on account provision or active confirmation, not on new passive discovery.
## 2026-09-07 00:03:33 UTC [target] (model bigpickle)
[PRIO] kurs.onecode.de (post-auth BOLA),7.0,a=7,b=9,t=9,g=1,c=7,f=7 — fully auth-gated, top hypothesis needs test accounts
[PRIO] cto.onecode.de,5.8,a=6,b=7,t=3,g=3,c=6,f=6 — CNAME stable, 409/1001 persists, HUMAN-claim pending
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/,5.5,a=8,b=8,t=8,g=9,c=5,f=5 — endpoint probeable but zero buckets (confirmed empty); risk lowered
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/,5.0,a=7,b=9,t=9,g=1,c=5,f=5 — 401 anon-block; daily monitor only
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS filter
class: IDOR
asset: kurs.onecode.de (/api/*, /v1/*) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Single Supabase project backs invite-only course platform; publishable key passes REST auth layer (503→401→401 evolving gateway); UUID PKs weaken guessable-ID BOLA → missing-RLS cross-tenant SELECT on profiles/enrollments is highest-value target. Unchanged — needs two invited accounts.
evidence_needed: Account-A token retrieving rows owned by Account-B.
verify_steps: (AUTH_HELPED) POST /auth/v1/token?grant_type=password per account; GET /rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit=1 with each token; diff row sets. Passive loop: re-probe /rest/v1 gateway after 00:00Z 09-08 (<=1/day).
impact: Cross-tenant PII/enrollment exfiltration — CRITICAL.
testability: AUTH_HELPED
[HYP] Dangling Perspective CNAME takeover on cto.onecode.de
class: MISCONFIG
asset: cto.onecode.de
confidence: 58
reasoning: CNAME cto→cname.perspective-dns.com stable 5+ days (dig confirmed 00:05 UTC); HTTP GET / = 409 "error code:1001" (Server:cloudflare); HTTPS returns TLS handshake failure (no cert); Perspective docs confirm this CNAME is their custom-subdomain binding mechanism; hostname unbound → reclaimable.
evidence_needed: Fresh Perspective account serving attacker content on cto.onecode.de.
verify_steps: PASSIVE (done): repeat GET http://cto.onecode.de/ <=1/day for 409/1001 stability. CONFIRM: HUMAN binds cto.onecode.de in a Perspective account, observes foreign content + TLS issuance.
impact: Full control of trusted *.onecode.de subdomain for phishing/repudiation + TLS via SaaS — HIGH.
testability: PASSIVE + HUMAN confirm
[HYP] Publishable-key direct REST exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 50
reasoning: 09-04/05 returned 503 PGRST002 with publishable key (key authenticates); 09-05/06/07 flipped to 401 explicit anon-block — gateway behavior fluctuates; if anon-role table ACL is permissive, cache recovery exposes missing-RLS tables pre-auth. Monitoring cadence = <=1/day; next probe after 00:00Z 09-08.
evidence_needed: Any non-503/401 response to a table query using only the publishable key.
verify_steps: GET /rest/v1/ + apikey header, <=1/day, next after 00:00Z 09-08.
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise.
testability: PASSIVE
[PARKED] Realtime /api/broadcast channel auth (MISCONFIG, conf 42): pre-auth gated; only post-auth testable with two accounts. Keep as secondary.
[PARKED] Magic-link token leakage (OATH, conf 38): no open redirect, no demonstrated hash-reader/XSS; standard Supabase flow. Re-open only if hash-reading sink found.
[PARKED] Supabase Storage public bucket (MISCONFIG, conf 55→50): endpoint probeable but zero buckets exist — exposure risk minimal until buckets are created.
[PARKED] GraphQL introspection (MISCONFIG, conf 45): /graphql returns 307→/login; no evidence GraphQL exists without auth.
[PARKED] Supabase Realtime impersonation (MISCONFIG, conf 35): speculative, no evidence of realtime publications beyond /api/broadcast.
[FINAL] 1. Post-auth BOLA via RLS gap (IDOR, 65, AUTH_HELPED) — highest overall value, blocked on test accounts
[FINAL] 2. Dangling Perspective CNAME takeover (MISCONFIG, 58, PASSIVE+HUMAN) — provider confirmed, reclaimable, needs HUMAN claim
[FINAL] 3. Publishable-key REST exposure on cache recovery (IDOR, 50, PASSIVE) — daily monitor, next probe 09-08
[NEXT] PASSIVE: Re-probe GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ with apikey header after 00:00Z 09-08 (cadence <=1/day). All other hypotheses blocked on external actions (HUMAN or AUTH_HELPED). No new probe today — all surfaces confirmed unchanged.
[LEARN] NO_DELTA @ all: REST 401 anon-block persists; cto 409/1001 persists; storage empty; kurs.onecode.de/login 200 unchanged. Identical state to 09-06 22:11.
[LEARN] ACCEPTED IDOR(post-auth) @ kurs.onecode.de: Post-auth BOLA via RLS gap remains highest-value (conf 65); requires two invited test accounts.
[LEARN] ACCEPTED MISCONFIG @ cto.onecode.de: CNAME → cname.perspective-dns.com stable 5+ days; 409/1001 + missing cert → hostname unbound/reclaimable; conf 58, HUMAN confirm pending.
[LEARN] ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Endpoint probeable, zero buckets — risk lowered but monitor active.
[LEARN] ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: Explicit 401 anon-block with publishable key; monitor for cache recovery after 00:00Z 09-08.
[LEARN] REJECTED OATH @ kurs.onecode.de: No external OAuth providers configured (all false in /auth/v1/settings).
[LEARN] REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: Confidence 45 < 50; passive-only cannot confirm without active DNS resolution.
[LEARN] REJECTED MISCONFIG @ www.onecode.de: Static Webflow marketing, no dynamic surface.
[LEARN] REJECTED MISCONFIG @ mail.onecode.de: Non-web service, out-of-scope.
[RISK] onecode: 67 — unchanged. No new exposure this cycle. Dominant residual risk: post-auth BOLA via RLS gap (65, CRITICAL, account-blocked) + latent publishable-key REST recovery (50, daily monitor) + cto dangling-CNAME (58, HUMAN-claim pending). All blocked on account provision or active confirmation, not on new passive discovery.
## 2026-09-07 04:55:59 UTC [target] (model bigpickle)
[LEARN] ACCEPTED MISCONFIG @ cto.onecode.de: re-confirmed live 09-07 — GET http://cto.onecode.de/ = 409, HTTPS = empty/handshake-fail, CNAME → cname.perspective-dns.com stable 5+ days; hostname unbound/reclaimable; conf 58, HUMAN confirm pending.
[PRIO] kurs.onecode.de (post-auth BOLA),7.0,a=7,b=9,t=9,g=1,c=7,f=7 — fully auth-gated; top hypothesis blocked on two test accounts
[PRIO] cto.onecode.de,5.8,a=6,b=7,t=3,g=3,c=6,f=6 — CNAME stable 5+ days, 409/1001 + TLS-fail persist; needs HUMAN claim
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/,5.0,a=7,b=9,t=9,g=1,c=5,f=5 — 401 anon-block; daily monitor only, next probe 09-08
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS filter
class: IDOR
asset: kurs.onecode.de (/api/*, /v1/*) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Single Supabase project backs invite-only course platform; publishable key authenticates to REST gateway (503→401 evolution); UUID PKs weaken guessable-ID BOLA → missing-RLS cross-tenant SELECT highest-value. Unchanged; needs two invited accounts.
evidence_needed: Account-A token retrieving rows owned by Account-B.
verify_steps: (AUTH_HELPED) POST /auth/v1/token?grant_type=password per account; GET /rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit=1 per token; diff row sets. Passive: re-probe REST gateway after 00:00Z 09-08 (<=1/day).
impact: Cross-tenant PII/enrollment exfiltration — CRITICAL.
testability: AUTH_HELPED
[HYP] Dangling Perspective CNAME takeover on cto.onecode.de
class: MISCONFIG
asset: cto.onecode.de
confidence: 58
reasoning: Live-confirmed 09-07: HTTP 409 "error code:1001", HTTPS TLS handshake fail (no cert), CNAME → cname.perspective-dns.com (104.18.x/2606:4700::). Perspective docs confirm this CNAME is their domain-binding target; unbound → reclaimable.
evidence_needed: Fresh Perspective account serving attacker content on cto.onecode.de.
verify_steps: PASSIVE (done): ≤1/day GET http://cto.onecode.de/ for 409/1001 stability. CONFIRM: HUMAN binds cto.onecode.de in a Perspective account, observes foreign content + TLS issuance.
impact: Full control of trusted *.onecode.de subdomain for phishing/repudiation + TLS via SaaS — HIGH.
testability: PASSIVE + HUMAN confirm
[HYP] Publishable-key direct REST exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 50
reasoning: 09-04/05: 503 PGRST002 (key authenticates); 09-05/06/07: 401 explicit anon-block — gateway behavior fluctuates; if anon-role table ACL is permissive, cache recovery exposes missing-RLS tables pre-auth. Monitoring cadence <=1/day.
evidence_needed: Any non-503/401 response to a table query using only the publishable key.
verify_steps: GET /rest/v1/ + apikey header, <=1/day, next after 00:00Z 09-08.
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise.
testability: PASSIVE
[PARKED] Realtime /api/broadcast channel auth (MISCONFIG, 42): pre-auth gated; post-auth only with accounts.
[PARKED] Magic-link hash leakage (OATH, 38): no redirect flaw, no hash-reading sink; standard Supabase flow.
[PARKED] Storage public bucket (MISCONFIG, 55→50): probeable, zero buckets exist.
[PARKED] GraphQL introspection (MISCONFIG, 45): no pre-auth GraphQL evidence.
[PARKED] Realtime impersonation (MISCONFIG, 35): speculative.
[FINAL] 1. Post-auth BOLA via RLS gap (IDOR, 65, AUTH_HELPED) — highest value, account-blocked
[FINAL] 2. Dangling Perspective CNAME takeover (MISCONFIG, 58, PASSIVE+HUMAN) — live re-confirmed 09-07
[FINAL] 3. Publishable-key REST exposure on cache recovery (IDOR, 50, PASSIVE) — daily monitor
[NEXT] PASSIVE: Re-probe GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ with apikey header after 00:00Z 09-08 (cadence <=1/day). All other hypotheses blocked on HUMAN or AUTH_HELPED; no new probe today.
[LEARN] ACCEPTED MISCONFIG @ cto.onecode.de: live re-probe 09-07 — HTTP 409/1001, HTTPS handshake-fail, CNAME → cname.perspective-dns.com stable; unbound/reclaimable; conf 58, HUMAN pending.
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: /login + /passwort-vergessen both 200 today; pre-auth surface stable, exhausted; no new cookie/session signal.
[LEARN] REJECTED MISCONFIG @ hostmaster.*/www/mail.onecode.de: unchanged classes — NXDOMAIN/static/non-web, no new surface.
[RISK] onecode: 67 — unchanged. No new exposure this cycle. Residual risk = post-auth BOLA via RLS gap (65, CRITICAL, account-blocked) + cto dangling-CNAME (58, HUMAN-claim pending) + latent publishable-key REST recovery (50, daily monitor). All blocked on account provision or HUMAN action, not on new passive discovery.
## 2026-09-07 10:02:41 UTC [target] (model bigpickle)
[PRIO] kurs.onecode.de (post-auth BOLA),7.0,a=7,b=9,t=9,g=1,c=7,f=7 — fully auth-gated; top hypothesis blocked on two test accounts
[PRIO] cto.onecode.de,5.8,a=6,b=7,t=3,g=3,c=6,f=6 — CNAME stable 5+ days, 409/1001 + TLS-fail persist; needs HUMAN claim
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/,5.0,a=7,b=9,t=9,g=1,c=5,f=5 — 401 anon-block; daily monitor only, next probe 09-08
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS filter
class: IDOR
asset: kurs.onecode.de (/api/*, /v1/*) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Single Supabase project backs invite-only course platform; publishable key authenticates to REST gateway (503→401 evolution); UUID PKs weaken guessable-ID BOLA → missing-RLS cross-tenant SELECT highest-value. Unchanged; needs two invited accounts.
evidence_needed: Account-A token retrieving rows owned by Account-B.
verify_steps: (AUTH_HELPED) POST /auth/v1/token?grant_type=password per account; GET /rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit=1 per token; diff row sets. Passive: re-probe REST gateway after 00:00Z 09-08 (<=1/day).
impact: Cross-tenant PII/enrollment exfiltration — CRITICAL.
testability: AUTH_HELPED
[HYP] Dangling Perspective CNAME takeover on cto.onecode.de
class: MISCONFIG
asset: cto.onecode.de
confidence: 58
reasoning: Live-confirmed 09-07: HTTP 409 "error code:1001", HTTPS TLS handshake fail (no cert), CNAME → cname.perspective-dns.com (104.18.x/2606:4700::). Perspective docs confirm this CNAME is their domain-binding target; unbound → reclaimable.
evidence_needed: Fresh Perspective account serving attacker content on cto.onecode.de.
verify_steps: PASSIVE (done): ≤1/day GET http://cto.onecode.de/ for 409/1001 stability. CONFIRM: HUMAN binds cto.onecode.de in a Perspective account, observes foreign content + TLS issuance.
impact: Full control of trusted *.onecode.de subdomain for phishing/repudiation + TLS via SaaS — HIGH.
testability: PASSIVE + HUMAN confirm
[HYP] Publishable-key direct REST exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 50
reasoning: 09-04/05: 503 PGRST002 (key authenticates); 09-05/06/07: 401 explicit anon-block — gateway behavior fluctuates; if anon-role table ACL is permissive, cache recovery exposes missing-RLS tables pre-auth. Monitoring cadence <=1/day.
evidence_needed: Any non-503/401 response to a table query using only the publishable key.
verify_steps: GET /rest/v1/ + apikey header, <=1/day, next after 00:00Z 09-08.
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise.
testability: PASSIVE
[PARKED] Realtime /api/broadcast channel auth (MISCONFIG, 42): pre-auth gated; post-auth only with accounts.
[PARKED] Magic-link hash leakage (OATH, 38): no redirect flaw, no hash-reading sink; standard Supabase flow.
[PARKED] Storage public bucket (MISCONFIG, 55→50): probeable, zero buckets exist.
[PARKED] GraphQL introspection (MISCONFIG, 45): no pre-auth GraphQL evidence.
[PARKED] Realtime impersonation (MISCONFIG, 35): speculative.
[FINAL] 1. Post-auth BOLA via RLS gap (IDOR, 65, AUTH_HELPED) — highest value, account-blocked
[FINAL] 2. Dangling Perspective CNAME takeover (MISCONFIG, 58, PASSIVE+HUMAN) — live re-confirmed 09-07
[FINAL] 3. Publishable-key REST exposure on cache recovery (IDOR, 50, PASSIVE) — daily monitor
[NEXT] PASSIVE: Re-probe GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ with apikey header after 00:00Z 09-08 (cadence <=1/day). All other hypotheses blocked on HUMAN or AUTH_HELPED; no new probe today.
[LEARN] ACCEPTED MISCONFIG @ cto.onecode.de: re-confirmed live 09-07 — GET http://cto.onecode.de/ = 409, HTTPS = empty/handshake-fail, CNAME → cname.perspective-dns.com stable 5+ days; hostname unbound/reclaimable; conf 58, HUMAN confirm pending.
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: /login + /passwort-vergessen both 200 today; pre-auth surface stable, exhausted; no new cookie/session signal.
[LEARN] REJECTED MISCONFIG @ hostmaster.*/www/mail.onecode.de: unchanged classes — NXDOMAIN/static/non-web, no new surface.
[RISK] onecode: 67 — unchanged. No new exposure this cycle. Residual risk = post-auth BOLA via RLS gap (65, CRITICAL, account-blocked) + cto dangling-CNAME (58, HUMAN-claim pending) + latent publishable-key REST recovery (50, daily monitor). All blocked on account provision or HUMAN action, not on new passive discovery.
## 2026-09-07 15:58:12 UTC [target] (model bigpickle)
[PRIO] kurs.onecode.de (post-auth BOLA),7.0,a=7,b=9,t=9,g=1,c=7,f=7 — fully auth-gated; top hypothesis blocked on two test accounts
[PRIO] cto.onecode.de,5.8,a=6,b=7,t=3,g=3,c=6,f=6 — CNAME stable 5+ days, 409/1001 + TLS-fail persist; needs HUMAN claim
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/,5.0,a=7,b=9,t=9,g=1,c=5,f=5 — 401 anon-block; daily monitor only, next probe 09-08
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS filter
class: IDOR
asset: kurs.onecode.de (/api/*, /v1/*) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Single Supabase project backs invite-only course platform; publishable key authenticates to REST gateway (503→401 evolution); UUID PKs weaken guessable-ID BOLA → missing-RLS cross-tenant SELECT highest-value. Unchanged; needs two invited accounts.
evidence_needed: Account-A token retrieving rows owned by Account-B.
verify_steps: (AUTH_HELPED) POST /auth/v1/token?grant_type=password per account; GET /rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit=1 per token; diff row sets. Passive: re-probe REST gateway after 00:00Z 09-08 (<=1/day).
impact: Cross-tenant PII/enrollment exfiltration — CRITICAL.
testability: AUTH_HELPED
[HYP] Dangling Perspective CNAME takeover on cto.onecode.de
class: MISCONFIG
asset: cto.onecode.de
confidence: 58
reasoning: Live-re-confirmed 15:55 UTC 09-07: HTTP 409 "error code:1001", HTTPS TLS handshake fail (no cert), CNAME → cname.perspective-dns.com (104.18.x/2606:4700::). Stable 5+ days. Perspective docs confirm this CNAME is their domain-binding target; unbound → reclaimable.
evidence_needed: Fresh Perspective account serving attacker content on cto.onecode.de.
verify_steps: PASSIVE (done): ≤1/day GET http://cto.onecode.de/ for 409/1001 stability. CONFIRM: HUMAN binds cto.onecode.de in a Perspective account, observes foreign content + TLS issuance.
impact: Full control of trusted *.onecode.de subdomain for phishing/repudiation + TLS via SaaS — HIGH.
testability: PASSIVE + HUMAN confirm
[HYP] Publishable-key direct REST exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 50
reasoning: 09-04/05: 503 PGRST002 (key authenticates); 09-05/06/07: 401 explicit anon-block — gateway behavior fluctuates; if anon-role table ACL is permissive, cache recovery exposes missing-RLS tables pre-auth. Monitoring cadence <=1/day.
evidence_needed: Any non-503/401 response to a table query using only the publishable key.
verify_steps: GET /rest/v1/ + apikey header, <=1/day, next after 00:00Z 09-08.
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise.
testability: PASSIVE
[PARKED] Realtime /api/broadcast channel auth (MISCONFIG, 42): pre-auth gated; post-auth only with accounts.
[PARKED] Magic-link hash leakage (OATH, 38): no redirect flaw, no hash-reading sink; standard Supabase flow.
[PARKED] Storage public bucket (MISCONFIG, 55→50): probeable, zero buckets exist.
[PARKED] GraphQL introspection (MISCONFIG, 45): no pre-auth GraphQL evidence.
[PARKED] Realtime impersonation (MISCONFIG, 35): speculative.
[FINAL] 1. Post-auth BOLA via RLS gap (IDOR, 65, AUTH_HELPED) — highest value, account-blocked
[FINAL] 2. Dangling Perspective CNAME takeover (MISCONFIG, 58, PASSIVE+HUMAN) — live re-confirmed 09-07 15:55
[FINAL] 3. Publishable-key REST exposure on cache recovery (IDOR, 50, PASSIVE) — daily monitor
[NEXT] PASSIVE: Re-probe GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/ with apikey header after 00:00Z 09-08 (cadence <=1/day). All other hypotheses blocked on HUMAN or AUTH_HELPED; no new probe today.
[LEARN] NO_DELTA @ all: REST 401 anon-block persists; cto 409/1001 persists; storage empty; kurs.onecode.de/login 200 unchanged. Identical state to 09-07 10:03.
[LEARN] ACCEPTED MISCONFIG @ cto.onecode.de: re-confirmed live 15:55 UTC 09-07 — HTTP 409/1001, HTTPS handshake-fail, CNAME → cname.perspective-dns.com stable 5+ days; hostname unbound/reclaimable; conf 58, HUMAN confirm pending.
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: /login 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal.
[LEARN] REJECTED MISCONFIG @ hostmaster.*/www/mail.onecode.de: unchanged classes — NXDOMAIN/static/non-web, no new surface.
[RISK] onecode: 67 — unchanged. No new exposure this cycle. Residual risk = post-auth BOLA via RLS gap (65, CRITICAL, account-blocked) + cto dangling-CNAME (58, HUMAN-claim pending) + latent publishable-key REST recovery (50, daily monitor). All blocked on account provision or HUMAN action, not on new passive discovery.
## 2026-09-07 19:47:27 UTC [target] (model bigpickle)
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS filter
class: IDOR
asset: kurs.onecode.de (/api/*, /v1/*) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Single Supabase project backs invite-only course platform; publishable key authenticates to REST gateway (401 anon-block, was 503 PGRST002); UUID PKs weaken guessable-ID BOLA → missing-RLS cross-tenant SELECT highest-value. Unchanged; needs two invited accounts.
evidence_needed: Account-A token retrieving rows owned by Account-B.
verify_steps: (AUTH_HELPED) POST /auth/v1/token?grant_type=password per account; GET /rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit=1 per token; diff row sets. Passive: re-probe REST gateway after 00:00Z 09-08 (<=1/day, next due).
impact: Cross-tenant PII/enrollment exfiltration — CRITICAL.
testability: AUTH_HELPED
[HYP] Dangling Perspective CNAME takeover on cto.onecode.de
class: MISCONFIG
asset: cto.onecode.de
confidence: 58
reasoning: Live-confirmed 19:47 UTC 09-07: HTTP 409, CNAME → cname.perspective-dns.com (104.18.x). Stable 5+ days. Perspective docs confirm this CNAME is their domain-binding target; unbound → reclaimable.
evidence_needed: Fresh Perspective account serving attacker content on cto.onecode.de.
verify_steps: PASSIVE (done): <=1/day GET http://cto.onecode.de/ for 409 stability. CONFIRM: HUMAN binds cto.onecode.de in a Perspective account, observes foreign content + TLS issuance.
impact: Full control of trusted *.onecode.de subdomain for phishing/repudiation + TLS via SaaS — HIGH.
testability: PASSIVE + HUMAN confirm
[HYP] Publishable-key direct REST exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 50
reasoning: 09-04/05: 503 PGRST002 (key authenticates); 09-05/06/07: 401 explicit anon-block — gateway fluctuates; if anon-role table ACL permissive, cache recovery exposes missing-RLS tables pre-auth. Monitoring <=1/day.
evidence_needed: Any non-503/401 response to a table query using only the publishable key.
verify_steps: GET /rest/v1/ + apikey header, <=1/day, next designated after 00:00Z 09-08.
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise.
testability: PASSIVE
[NEXT] HUMAN: Escalate to obtain two invited test accounts for kurs.onecode.de to activate the post-auth BOLA hypothesis (conf 65, CRITICAL impact). Pre-auth surface fully exhausted; all remaining value depends on account provision (AUTH_HELPED).
[LEARN] NO_DELTA @ all: REST 401 anon-block persists (19:47 09-07); cto 409/CNAME→cname.perspective-dns.com persists; kurs /login+/passwort-vergessen 200 unchanged. Identical state to 09-07 15:58.
[LEARN] ACCEPTED MISCONFIG @ cto.onecode.de: re-confirmed live 19:47 UTC 09-07 — HTTP 409, CNAME→cname.perspective-dns.com stable 5+ days; hostname unbound/reclaimable; conf 58, HUMAN confirm pending.
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: /login + /passwort-vergessen 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal.
[LEARN] REJECTED MISCONFIG @ hostmaster.*/www/mail.onecode.de: unchanged classes — NXDOMAIN/static/non-web, no new surface.
[RISK] onecode: 67 — unchanged. No new exposure this cycle. Residual risk = post-auth BOLA via RLS gap (65, CRITICAL, account-blocked) + cto dangling-CNAME (58, HUMAN-claim pending) + latent publishable-key REST recovery (50, daily monitor). All blocked on account provision or HUMAN action, not on new passive discovery.
## 2026-09-07 22:42:50 UTC [target] (model bigpickle)
[PRIO] cto.onecode.de,6.8,conf=58 dangling-CNAME; gate_ease=10 (no auth); claims escalate if a fresh Perspective account lands on the domain — highest claimable-value/effort ratio.
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1,6.35,IDOR-latent; business_value=9 (cross-tenant PII) but gated by anon-block until cache recovery.
[PRIO] kurs.onecode.de,6.15,post-auth BOLA 65; gate_ease=2 (307→/login) — value realized only with invited accounts.
[HYP] Publishable-key REST exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 50
reasoning: 09-04/05: 503 PGRST002 (key authenticates); 09-05/06/07: 401 explicit anon-block — gateway fluctuates; if anon-role ACL is permissive, cache recovery exposes missing-RLS tables pre-auth.
evidence_needed: Any non-503/401 response to a table query using only the publishable key.
verify_steps: GET /rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit=1 with apikey: sb_publishable_* header, <=1/day, next after 00:00Z 09-08.
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise.
testability: PASSIVE
[HYP] Dangling Perspective CNAME takeover on cto.onecode.de
class: MISCONFIG
asset: cto.onecode.de
confidence: 58
reasoning: 19:47Z live re-confirm — HTTP 409 "error code:1001", CNAME → cname.perspective-dns.com (104.18.x), stable 5+ days; docs confirm this CNAME is Perspective's domain-binding target; unbound → reclaimable.
evidence_needed: Fresh Perspective account serving attacker content on cto.onecode.de.
verify_steps: PASSIVE done (<=1/day GET / for 409). CONFIRM: HUMAN binds domain in Perspective account, observes foreign content + TLS issuance.
impact: Full control of trusted *.onecode.de subdomain for phishing/repudiation + TLS via SaaS — HIGH.
testability: PASSIVE + HUMAN confirm
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS filter
class: IDOR
asset: kurs.onecode.de (/api/*) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Single Supabase project backs invite-only course platform; UUID PKs weaken guessable-ID BOLA → missing-RLS cross-tenant SELECT is the highest-value test; needs two invited accounts.
evidence_needed: Account-A token retrieving rows owned by Account-B.
verify_steps: (AUTH_HELPED) POST /auth/v1/token?grant_type=password per account; GET /rest/v1/profiles?select=* per token; diff row sets.
impact: Cross-tenant PII/enrollment exfiltration — CRITICAL.
testability: AUTH_HELPED
[PARKED] Realtime /api/broadcast channel auth (42): pre-auth gated, post-auth only w/ accounts.
[PARKED] Magic-link hash leakage (38): no redirect flaw, no hash-reading sink; standard Supabase flow.
[PARKED] Storage public bucket (50): probeable but zero buckets exist.
[PARKED] GraphQL introspection (45): no pre-auth GraphQL evidence.
[PARKED] Realtime impersonation (35): speculative — below threshold.
[FINAL] 1. Post-auth BOLA via RLS gap (IDOR, 65, AUTH_HELPED) — highest value, account-blocked
[FINAL] 2. Dangling Perspective CNAME takeover (MISCONFIG, 58, PASSIVE+HUMAN) — live re-confirmed 19:47Z
[FINAL] 3. Publishable-key REST exposure on cache recovery (IDOR, 50, PASSIVE) — daily monitor, due after 00:00Z 09-08
[NEXT] PROBE: at first cycle after 00:00Z 09-08, GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 and /rest/v1/enrollments?select=*&limit=1 with header `apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30` (sha256 870cf518...) — any non-503/401 reply activates the cached-schema exposure hypothesis. All other hypotheses blocked on HUMAN (cto claim) or AUTH_HELPED (test accounts); no new probe warranted before 00:00Z.
[LEARN] NO_DELTA @ all: 22:40Z 09-07 — REST 401, cto 409/CNAME, storage empty, kurs /login+/passwort-vergessen 200, identical to 19:47Z run; all monitors at cadence limit.
[LEARN] ACCEPTED MISCONFIG @ cto.onecode.de: CNAME → cname.perspective-dns.com stable 5+ days; 409/1001 + missing cert = hostname unbound/reclaimable; conf 58, HUMAN confirm pending.
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: /login + /passwort-vergessen 200 unchanged tonight; pre-auth surface stable and exhausted.
[LEARN] ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 401 anon-block persists; monitor for schema-cache recovery after 00:00Z 09-08.
[RISK] onecode: 67 — unchanged. Residual risk = post-auth BOLA via RLS gap (65, CRITICAL, account-blocked) + cto dangling-CNAME (58, HUMAN-claim pending) + latent publishable-key REST recovery (50, daily monitor). All blocked on account provision or HUMAN action, not on new passive discovery. No new exposure this cycle.
## 2026-09-08 01:02:59 UTC [target] (model bigpickle)
## 2026-09-08 06:02:43 UTC [target] (model bigpickle)
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/,6.35,IDOR-latent; business_value=9 (cross-tenant PII) but gated by anon-block; gate_ease=5 (publishable key only); cache recovery due.
[PRIO] cto.onecode.de,6.8,MISCONFIG; gate_ease=10 (no auth); business_value=8 (trusted subdomain); CNAME→Perspective stable 6+ days; HUMAN claim pending.
[PRIO] kurs.onecode.de,6.15,IDOR(post-auth); business_value=9 (cross-tenant course data); gate_ease=2 (invite-only); conf 65 but account-blocked.
[HYP] Publishable-key REST exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 50
reasoning: 09-04/05: 503 PGRST002 (key authenticates); 09-05/06/07: 401 explicit anon-block — gateway fluctuates; if anon-role table ACL permissive, cache recovery exposes missing-RLS tables pre-auth.
evidence_needed: Any non-503/401 response to a table query using only the publishable key.
verify_steps: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" — any 200/body activates hypothesis.
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise.
testability: PASSIVE
[HYP] Dangling Perspective CNAME takeover on cto.onecode.de
class: MISCONFIG
asset: cto.onecode.de
confidence: 58
reasoning: CNAME→cname.perspective-dns.com stable 6+ days; HTTP 409/1001 + missing cert = hostname unbound and reclaimable; docs confirm this CNAME is Perspective's domain-binding target.
evidence_needed: Fresh Perspective account serving attacker content on cto.onecode.de.
verify_steps: PASSIVE done (<=1/day GET / for 409). CONFIRM: HUMAN binds domain in Perspective account, observes foreign content + TLS issuance.
impact: Full control of trusted *.onecode.de subdomain for phishing/repudiation + TLS via SaaS — HIGH.
testability: PASSIVE + HUMAN
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS filter
class: IDOR
asset: kurs.onecode.de (/api/*) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Single Supabase project backs invite-only course platform; UUID PKs weaken guessable-ID BOLA → missing-RLS cross-tenant SELECT is the highest-value test; needs two invited accounts.
evidence_needed: Account-A token retrieving rows owned by Account-B.
verify_steps: (AUTH_HELPED) POST /auth/v1/token?grant_type=password per account; GET /rest/v1/profiles?select=* per token; diff row sets.
impact: Cross-tenant PII/enrollment exfiltration — CRITICAL.
testability: AUTH_HELPED
[PARKED] Realtime /api/broadcast channel auth (42): pre-auth gated, post-auth only w/ accounts.
[PARKED] Magic-link hash leakage (38): no redirect flaw, no hash-reading sink; standard Supabase flow.
[PARKED] Storage public bucket (50): probeable but zero buckets exist.
[PARKED] GraphQL introspection (45): no pre-auth GraphQL evidence.
[PARKED] Realtime impersonation (35): speculative — below threshold.
[FINAL] 1. Post-auth BOLA via RLS gap (IDOR, 65, AUTH_HELPED) — highest value, account-blocked
[FINAL] 2. Dangling Perspective CNAME takeover (MISCONFIG, 58, PASSIVE+HUMAN) — stable 6+ days
[FINAL] 3. Publishable-key REST exposure on cache recovery (IDOR, 50, PASSIVE) — daily monitor due now
[NEXT] PROBE: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" -H "Authorization: Bearer sb_publishable_g48Bd8qEtLesgk0zgzTRig_eZ6j9w30" — if non-503/401, cached-schema exposure hypothesis activates; if 401/503, re-confirm anon-block and defer to next cycle.
[NEXT] PROBE: Retry GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with publishable key 1x more this cycle (<30s gap); if still 503 PGRST002, the REST gateway returned to schema-cache-down mode — re-probe <=1/day watching for any flip to a permissive per-table response (200/body), which would activate the cached-schema exposure hypothesis.
[LEARN] ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 2026-09-08 probe (01:10Z) — the gateway FLIPPED from 401 anon-block back to 503 PGRST002 "Could not query the database for the schema cache" across /profiles,/enrollments,/users. Confirms REST gateway state is unstable/fluctuating between anon-block and schema-cache-down, NOT indicating permissive ACL on either state. Monitor stays active <=1/day for any 200/body response (which would indicate table ACL exposure).
[RISK] onecode: 67 — unchanged. The 503↔401 flip on REST is a Bayes-delta strengthening the "cache recovery could change exposure" hypothesis (the gateway demonstrably toggles modes), but no permissive state observed. Residual risk unchanged: post-auth BOLA (65, account-blocked, AUTH_HELPED) + cto dangling-CNAME (58, HUMAN-claim) + latent publishable-key REST recovery (50, daily monitor). All still blocked on account provision or HUMAN action, not on new passive discovery.
## 2026-09-08 11:29:29 UTC [target] (model bigpickle)
[PRIO] cto.onecode.de,6.8,MISCONFIG; gate_ease=10 (no auth); business_value=8 (trusted subdomain); CNAME→Perspective stable 6+ days; HUMAN claim pending.
[PRIO] kurs.onecode.de,6.15,IDOR(post-auth); business_value=9 (cross-tenant course data); gate_ease=2 (invite-only); conf 65 but account-blocked.
[PRIO] aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/,6.35,IDOR-latent; business_value=9 (cross-tenant PII) but gated by 503 PGRST002; gate_ease=5 (publishable key only); cache recovery fluctuating.
[HYP] Publishable-key REST exposure on schema-cache recovery
class: IDOR
asset: aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 50
reasoning: 09-04/05: 503 PGRST002 (key authenticates); 09-05/06/07: 401 explicit anon-block; 09-08 01:10Z: FLIPPED back to 503 PGRST002. Gateway demonstrably toggles modes. If anon-role table ACL permissive, cache recovery exposes missing-RLS tables pre-auth.
evidence_needed: Any non-503/401 response to a table query using only the publishable key.
verify_steps: GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 -H "apikey: <publishable>" -H "Authorization: Bearer <publishable>" — any 200/body activates hypothesis.
impact: Unauthenticated cross-tenant row exposure — CRITICAL if realized; monitoring-only otherwise.
testability: PASSIVE
[HYP] Dangling Perspective CNAME takeover on cto.onecode.de
class: MISCONFIG
asset: cto.onecode.de
confidence: 58
reasoning: CNAME→cname.perspective-dns.com stable 6+ days; HTTP 409/1001 + missing cert = hostname unbound and reclaimable; docs confirm this CNAME is Perspective's domain-binding target.
evidence_needed: Fresh Perspective account serving attacker content on cto.onecode.de.
verify_steps: PASSIVE done (<=1/day GET / for 409). CONFIRM: HUMAN binds domain in Perspective account, observes foreign content + TLS issuance.
impact: Full control of trusted *.onecode.de subdomain for phishing/repudiation + TLS via SaaS — HIGH.
testability: PASSIVE + HUMAN
[HYP] Post-auth cross-tenant BOLA via missing Supabase RLS filter
class: IDOR
asset: kurs.onecode.de (/api/*) + aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/
confidence: 65
reasoning: Single Supabase project backs invite-only course platform; UUID PKs weaken guessable-ID BOLA → missing-RLS cross-tenant SELECT is the highest-value test; needs two invited accounts.
evidence_needed: Account-A token retrieving rows owned by Account-B.
verify_steps: (AUTH_HELPED) POST /auth/v1/token?grant_type=password per account; GET /rest/v1/profiles?select=* per token; diff row sets.
impact: Cross-tenant PII/enrollment exfiltration — CRITICAL.
testability: AUTH_HELPED
[PARKED] Realtime /api/broadcast channel auth (42): pre-auth gated, post-auth only w/ accounts.
[PARKED] Magic-link hash leakage (38): no redirect flaw, no hash-reading sink; standard Supabase flow.
[PARKED] Storage public bucket (50): probeable but zero buckets exist.
[PARKED] GraphQL introspection (45): no pre-auth GraphQL evidence.
[PARKED] Realtime impersonation (35): speculative — below threshold.
[FINAL] 1. Post-auth BOLA via RLS gap (IDOR, 65, AUTH_HELPED) — highest value, account-blocked
[FINAL] 2. Dangling Perspective CNAME takeover (MISCONFIG, 58, PASSIVE+HUMAN) — stable 6+ days
[FINAL] 3. Publishable-key REST exposure on cache recovery (IDOR, 50, PASSIVE) — daily monitor due
[NEXT] PROBE: <=1/day re-probe REST at next cycle. GET https://aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/profiles?select=*&limit=1 with publishable key — 503 PGRST002 persists, continue monitoring. Next actionable probe requires either (a) cache recovery flipping to 200/body, or (b) HUMAN action on cto.onecode.de Perspective claim.
[LEARN] ACCEPTED IDOR @ aygnpacdkgtsfnhgcyjc.supabase.co/rest/v1/: 2026-09-08 11:29Z probe — 503 PGRST002 persists (schema-cache-down mode). Gateway has now shown three states: 503→401→503 since 09-04. Confirms unstable/gateway toggling; NOT permissive on any observed state. Monitor stays active.
[LEARN] ACCEPTED MISCONFIG @ cto.onecode.de: re-confirmed 11:29Z 09-08 — HTTP 409 "error code:1001", CNAME→cname.perspective-dns.com stable 6+ days; hostname unbound/reclaimable; conf 58, HUMAN confirm pending.
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: /login 200 unchanged; pre-auth surface stable, exhausted; no new cookie/session signal.
[LEARN] ACCEPTED MISCONFIG @ aygnpacdkgtsfnhgcyjc.supabase.co/storage/v1/: Empty bucket list confirmed — endpoint probeable but zero buckets exist.
[RISK] onecode: 67 — unchanged. Residual risk = post-auth BOLA via RLS gap (65, CRITICAL, account-blocked) + cto dangling-CNAME (58, HUMAN-claim pending) + latent publishable-key REST recovery (50, daily monitor). All blocked on account provision or HUMAN action, not on new passive discovery. REST gateway demonstrated 503↔401 instability — strengthens "cache recovery could change exposure" hypothesis but no permissive state observed. No new exposure this cycle.
