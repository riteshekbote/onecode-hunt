# Knowledge Base (seed)
- 2026-09-03 REJECTED XSS/IDOR/SSRF/OATH @ api: no endpoints identified yet
- 2026-09-03 ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface
- 2026-09-03 REJECTED MISCONFIG @ hostmaster.*/cto.onecode.de: confidence below threshold (45), passive-only verification cannot confirm takeover without active DNS resolution against provider APIs; parked for future re-evaluation if CNAME targets identified.
- 2026-09-03 ACCEPTED AUTH @ kurs.onecode.de: Railway-hosted apps with 307 login redirect are high-value for session fixation/IDOR; tech_exposure=8 (Railway, auth flow, likely API).
- 2026-09-03 ACCEPTED IDOR @ kurs.onecode.de: Course platform semantics (enrollments, resources) strongly predict IDOR; gate_ease=9 (login required but test account feasible).
- 2026-09-03 ACCEPTED MISCONFIG @ kurs.onecode.de: Railway app likely has API surface (from bigpickle).
