## 2026-09-03 16:16:08 UTC [target] (model nemotron3)
[PRIO] kurs.onecode.de,8.5,a=9,b=9,t=8,g=9,c=7,f=6  
[PRIO] onecode.de,5.5,a=6,b=7,t=4,g=6,c=5,f=5  
[PRIO] www.onecode.de,3.5,a=4,b=5,t=3,g=5,c=4,f=4  
[PRIO] mail.onecode.de,3.0,a=5,b=6,t=2,g=4,c=3,f=3  
[PRIO] cto.onecode.de,2.5,a=4,b=5,t=2,g=3,c=2,f=2  
[PRIO] mta-sts.onecode.de,1.5,a=2,b=2,t=1,g=5,c=2,f=2  
[HYP] Railway-hosted auth bypass via session fixation on kurs.onecode.de  
class: AUTH  
asset: kurs.onecode.de  
confidence: 65  
reasoning: Host runs on Railway (tgk4io5m.up.railway.app), serves 307 redirect to /login with railway-hikari server header. Railway apps commonly use cookie-based sessions; if session ID not regenerated post-login, fixation possible. No rate-limit headers observed in passive scan.  
evidence_needed: Set-Cookie header on /login response pre-auth; session ID reuse after successful login; absence of Secure/HttpOnly/SameSite on session cookie  
verify_steps: GET https://kurs.onecode.de/login (capture Set-Cookie); POST /login with valid creds (test account) observe if session ID changes; check cookie attributes  
impact: ATO on customer portal → course access, PII, payment data — HIGH  
testability: AUTH_HELPED  
[HYP] IDOR on course enrollment/resource access via predictable IDs on kurs.onecode.de  
class: IDOR  
asset: kurs.onecode.de  
confidence: 60  
reasoning: Course platforms typically use numeric/UUID resource IDs (course_id, user_id, enrollment_id). Railway backend suggests REST/GraphQL API. No auth on passive probe but 307 to /login implies protected resources.  
evidence_needed: Authenticated session; API endpoints accepting id/uid/course_id/enrollment_id params; cross-user access to enrollments/content  
verify_steps: GET https://kurs.onecode.de/api/* (enumerate via JS source/Network tab); authenticated GET /api/courses/{id} with other users' IDs; check for /api/v1, /api/v2, /graphql endpoints  
impact: Cross-tenant PII dump, unauthorized course access, enrollment manipulation — HIGH  
testability: AUTH_HELPED  
[HYP] Subdomain takeover risk on unprobed hostmaster.* / cto.onecode.de via dangling CNAME  
class: MISCONFIG  
asset: hostmaster.onecode.de, hostmaster.www.onecode.de, hostmaster.hostmaster.onecode.de, hostmaster.hostmaster.www.onecode.de, cto.onecode.de  
confidence: 45  
reasoning: 5 hosts unprobed in passive recon; hostmaster.* often point to DNS/mail providers (e.g., Cloudflare, Google Workspace); cto.onecode.de could point to personal/dev infra. Wildcard-dominated zone per dedicated-deep.md increases takeover surface.  
evidence_needed: CNAME targets for each unprobed host; verify if target service allows claim (e.g., GitHub Pages, Heroku, Railway, AWS S3)  
verify_steps: dig +short CNAME hostmaster.onecode.de; dig +short CNAME cto.onecode.de; check each CNAME target for claimability  
impact: Full subdomain control → phishing, credential harvest, brand damage — CRITICAL  
testability: PASSIVE  
[PARKED] Subdomain takeover risk on unprobed hostmaster.* / cto.onecode.de via dangling CNAME: confidence 45 < 50 threshold; passive-only verify step insufficient to confirm claimability without active DNS interaction; requires live CNAME resolution which may touch provider APIs.  
[FINAL]  
[NEXT] PROBE: GET https://kurs.onecode.de/login — capture Set-Cookie headers, response body (CSRF token, form structure), security headers (CSP, HSTS, X-Frame-Options), and any version/debug info in HTML/JS. Single read-only request, <=1 rps.
[LEARN] REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: confidence below threshold (45), passive-only verification cannot confirm takeover without active DNS resolution against provider APIs; parked for future re-evaluation if CNAME targets identified.  
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: Railway-hosted apps with 307 login redirect are high-value for session fixation/IDOR; tech_exposure=8 (Railway, auth flow, likely API).  
[LEARN] ACCEPTED IDOR @ kurs.onecode.de: Course platform semantics (enrollments, resources) strongly predict IDOR; gate_ease=9 (login required but test account feasible).
[RISK] onecode: 75 — Primary asset (kurs.onecode.de) is a Railway-hosted customer portal with authentication, payments, and PII; two high-confidence hypotheses (AUTH, IDOR) with clear verify paths; unprobed subdomains (5) add takeover surface; wildcard DNS limits subdomain enumeration but focuses attack on known live assets.
## 2026-09-03 19:28:04 UTC [target] (model nemotron3)
[PRIO] kurs.onecode.de,8.4,a=9,b=9,t=8,g=9,c=7,f=6  
[PRIO] onecode.de,5.8,a=6,b=7,t=4,g=6,c=5,f=5  
[PRIO] www.onecode.de,4.3,a=4,b=5,t=3,g=5,c=4,f=4  
[PRIO] mail.onecode.de,3.8,a=5,b=6,t=2,g=4,c=3,f=3  
[PRIO] cto.onecode.de,2.8,a=4,b=5,t=2,g=3,c=2,f=2  
[PRIO] mta-sts.onecode.de,1.8,a=2,b=2,t=1,g=5,c=2,f=2
[HYP] Session fixation via pre-auth cookie reuse on Railway-hosted kurs.onecode.de
class: AUTH
asset: kurs.onecode.de
confidence: 65
reasoning: Host runs on Railway (tgk4io5m.up.railway.app), serves 307 redirect to /login with railway-hikari server header. Railway apps commonly use cookie-based sessions; if session ID not regenerated post-login, fixation possible. No rate-limit headers observed in passive scan.
evidence_needed: Set-Cookie header on /login response pre-auth; session ID reuse after successful login; absence of Secure/HttpOnly/SameSite on session cookie
verify_steps: GET https://kurs.onecode.de/login (capture Set-Cookie); POST /login with valid creds (test account) observe if session ID changes; check cookie attributes
impact: ATO on customer portal → course access, PII, payment data — HIGH
testability: AUTH_HELPED
[HYP] IDOR on course enrollment/resource access via predictable IDs on kurs.onecode.de
class: IDOR
asset: kurs.onecode.de
confidence: 60
reasoning: Course platforms typically use numeric/UUID resource IDs (course_id, user_id, enrollment_id). Railway backend suggests REST/GraphQL API. No auth on passive probe but 307 to /login implies protected resources.
evidence_needed: Authenticated session; API endpoints accepting id/uid/course_id/enrollment_id params; cross-user access to enrollments/content
verify_steps: GET https://kurs.onecode.de/api/* (enumerate via JS source/Network tab); authenticated GET /api/courses/{id} with other users' IDs; check for /api/v1, /api/v2, /graphql endpoints
impact: Cross-tenant PII dump, unauthorized course access, enrollment manipulation — HIGH
testability: AUTH_HELPED
[HYP] GraphQL introspection enabled on kurs.onecode.de API endpoint
class: MISCONFIG
asset: kurs.onecode.de
confidence: 45
reasoning: Railway-hosted Node.js/TypeScript apps frequently expose GraphQL at /graphql or /api/graphql with introspection enabled by default. No API endpoints identified yet in passive recon.
evidence_needed: 200 OK with __schema response on GET/POST to /graphql or /api/graphql; introspection query returns types/queries/mutations
verify_steps: GET https://kurs.onecode.de/graphql (HEAD first); if 200/400, POST {"query":"{__schema{types{name}}}"} to confirm introspection
impact: Full API schema leak → hidden mutations, admin operations, BOLA paths — HIGH
testability: PASSIVE
[PARKED] GraphQL introspection enabled on kurs.onecode.de API endpoint: confidence 45 < 50 threshold; no evidence GraphQL exists; verify step speculative without endpoint confirmation.
[FINAL] 
[NEXT] PROBE: GET https://kurs.onecode.de/login — capture Set-Cookie headers, response body (CSRF token, form structure), security headers (CSP, HSTS, X-Frame-Options), and any version/debug info in HTML/JS. Single read-only request, <=1 rps.
[LEARN] REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: confidence below threshold (45), passive-only verification cannot confirm takeover without active DNS resolution against provider APIs; parked for future re-evaluation if CNAME targets identified.
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: Railway-hosted apps with 307 login redirect are high-value for session fixation/IDOR; tech_exposure=8 (Railway, auth flow, likely API).
[LEARN] ACCEPTED IDOR @ kurs.onecode.de: Course platform semantics (enrollments, resources) strongly predict IDOR; gate_ease=9 (login required but test account feasible).
[LEARN] ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface (from bigpickle).
[RISK] onecode: 75 — Primary asset (kurs.onecode.de) is a Railway-hosted customer portal with authentication, payments, and PII; two high-confidence hypotheses (AUTH, IDOR) with clear verify paths; unprobed subdomains (5) add takeover surface; wildcard DNS limits subdomain enumeration but focuses attack on known live assets.
## 2026-09-03 21:53:56 UTC [target] (model nemotron3)
[NEW] Probe completed: GET https://kurs.onecode.de/login returns 200 with Next.js login form (email/password), no Set-Cookie header, no visible CSRF token in form. Root /, /api, /graphql, /dashboard all 307→/login (auth-gated). App branding: "Rich Dev Poor Dev" (invite-only course platform).
[PRIO] kurs.onecode.de,8.4,a=9,b=9,t=8,g=9,c=7,f=6
[PRIO] onecode.de,5.8,a=6,b=7,t=4,g=6,c=5,f=5
[PRIO] www.onecode.de,4.3,a=4,b=5,t=3,g=5,c=4,f=4
[PRIO] mail.onecode.de,3.8,a=5,b=6,t=2,g=4,c=3,f=3
[PRIO] cto.onecode.de,2.8,a=4,b=5,t=2,g=3,c=2,f=2
[PRIO] mta-sts.onecode.de,1.8,a=2,b=2,t=1,g=5,c=2,f=2
[HYP] Session fixation via pre-auth cookie reuse on Railway-hosted kurs.onecode.de
class: AUTH
asset: kurs.onecode.de
confidence: 60
reasoning: Host runs on Railway (railway-hikari), serves Next.js login at /login with 307 redirect from root. No Set-Cookie on GET /login. Railway/Next.js apps commonly use cookie-based sessions (next-auth, iron-session, or custom). If session ID not regenerated post-login, fixation possible.
evidence_needed: Set-Cookie header on POST /login response with valid creds; compare session ID before/after auth; check cookie attributes (Secure, HttpOnly, SameSite)
verify_steps: POST https://kurs.onecode.de/login with valid test credentials (capture Set-Cookie); GET /dashboard with pre-auth cookie to test fixation; inspect cookie flags
impact: ATO on customer portal → course access, PII, payment data — HIGH
testability: AUTH_HELPED
[HYP] IDOR on course enrollment/resource access via predictable IDs on kurs.onecode.de
class: IDOR
asset: kurs.onecode.de
confidence: 60
reasoning: Course platform semantics (enrollments, resources, dashboard) strongly predict IDOR. Next.js app likely has API routes under /api/* (protected by 307). Numeric/UUID resource IDs (course_id, user_id, enrollment_id) typical. Invite-only suggests multi-tenant.
evidence_needed: Authenticated session; API endpoints accepting id/uid/course_id/enrollment_id params; cross-user access to enrollments/content
verify_steps: Authenticated GET /api/courses (enumerate via JS source/Network); authenticated GET /api/courses/{other_user_id} to test cross-tenant access; check for /api/v1, /api/v2 patterns
impact: Cross-tenant PII dump, unauthorized course access, enrollment manipulation — HIGH
testability: AUTH_HELPED
[HYP] Missing rate limiting on login endpoint enabling credential stuffing on kurs.onecode.de
class: AUTH
asset: kurs.onecode.de
confidence: 50
reasoning: Login form at /login accepts email/password POST. No rate-limit headers observed (Retry-After, X-RateLimit-*) on GET /login or in response headers. Railway/Next.js default configs often lack brute-force protection. Invite-only platform makes valid email enumeration valuable.
evidence_needed: Multiple failed POST /login attempts without 429/lockout; absence of rate-limit headers; account lockout threshold
verify_steps: POST https://kurs.onecode.de/login with invalid creds 10x rapidly (observe status/headers); check for CAPTCHA, delays, or account lockout
impact: Credential stuffing → ATO on invite-only platform — MEDIUM
testability: PASSIVE
[PARKED] Session fixation via pre-auth cookie reuse on Railway-hosted kurs.onecode.de: requires valid test credentials to verify session ID regeneration; cannot confirm without AUTH_HELPED step.
[PARKED] IDOR on course enrollment/resource access via predictable IDs on kurs.onecode.de: requires authenticated session to enumerate API and test cross-tenant access; cannot confirm without AUTH_HELPED step.
[PARKED] GraphQL introspection enabled on kurs.onecode.de API endpoint: confidence 45 < 50; /graphql returns 307→/login; no evidence GraphQL exists without auth.
[FINAL] 
[NEXT] PROBE: POST https://kurs.onecode.de/login — with test credentials (if available) to capture Set-Cookie headers, session ID regeneration behavior, cookie attributes (Secure/HttpOnly/SameSite), and any rate-limit response headers. Single request, <=1 rps.
[LEARN] ACCEPTED AUTH @ kurs.onecode.de: Railway-hosted Next.js app with 307 login redirect confirmed; tech_exposure=8 (Railway, Next.js, auth flow, likely API surface).
[LEARN] ACCEPTED IDOR @ kurs.onecode.de: Course platform semantics confirmed (Rich Dev Poor Dev, invite-only, dashboard/enrollments); gate_ease=9 (test account feasible).
[LEARN] ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app has API surface (all /api/*, /graphql, /dashboard gated by 307).
[LEARN] REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: confidence below threshold (45), passive-only verification cannot confirm takeover without active DNS resolution.
[RISK] onecode: 75 — Primary asset (kurs.onecode.de) is Railway-hosted Next.js customer portal with auth, payments, PII; two high-confidence hypotheses (AUTH session fixation, IDOR) with clear verify paths requiring test credentials; unprobed subdomains (5) add takeover surface; wildcard DNS limits enumeration but focuses attack on known live assets.
