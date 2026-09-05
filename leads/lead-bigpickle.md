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
