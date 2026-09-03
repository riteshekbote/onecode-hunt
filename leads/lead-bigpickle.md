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
