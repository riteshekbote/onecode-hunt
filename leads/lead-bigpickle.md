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
