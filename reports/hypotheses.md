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
