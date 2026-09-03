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
