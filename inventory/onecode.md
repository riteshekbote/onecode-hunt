# OneCode GmbH inventory (discovered 2026-09-02)

cto.onecode.de
hostmaster.hostmaster.onecode.de
hostmaster.hostmaster.www.onecode.de
hostmaster.onecode.de
hostmaster.www.onecode.de
kurs.onecode.de
mail.onecode.de
mta-sts.onecode.de
onecode.de
www.onecode.de

## PASSIVE RECON 2026-09-02 (read-only, non-intrusive)

> Recon observations only. These are NOT confirmed vulnerabilities; ownership/in-scope of each host must be confirmed against the program scope before any active testing. Hosts resolve + serve HTTP — investigation requires scoped authorization.

**Probed:** 10 hosts | **Live HTTP:** 3

| Host | Status | Server/Tech |
|---|---|---|
| `kurs.onecode.de` | 307 | Server: railway-hikari -> /login |
| `www.onecode.de` | 200 | Server: cloudflare |
| `mta-sts.onecode.de` | 301 | Server: cloudflare -> https://www.onecode.de/ |

**CNAME review signals (3):**
- `kurs.onecode.de` -> `tgk4io5m.up.railway.app`
- `www.onecode.de` -> `cdn.webflow.com`
- `mta-sts.onecode.de` -> `cdn.webflow.com`
