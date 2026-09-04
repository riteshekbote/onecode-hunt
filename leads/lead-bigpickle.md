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
