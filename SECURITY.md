# Security Policy

Security and reliability are core requirements of the Darknode ecosystem.  
We welcome all responsible disclosures and will respond to every valid report.

---

## Supported Versions

Because this client is under active development, only the **latest release** is supported for security reports.

```
✔ Latest version (supported)
✘ Older versions (not supported)
✘ Forks / modified builds (not supported)
```

---

## Reporting a Vulnerability

If you discover a security issue, please report it responsibly.

### 📬 Contact (preferred)
```
security@darknode.tech
```

Encrypted reports are preferred.  
Public PGP key (Build & Security Key):

➡️ `docs/KEYS/DARKNODE_BUILD.asc`  
➡️ Fingerprint: **D5B4 67C1 4447 AC02 A76E  BC77 52A3 8DDA 6F8D 664F**

### 🛡 GitHub Security Advisories (recommended)
You may also report via:

```
GitHub → Security → Advisories → New draft advisory
```

---

## What to Include in Your Report

Please include (when possible):

1. Description of the issue  
2. Steps to reproduce  
3. Expected vs. actual behavior  
4. Potential impact  
5. Any PoC (proof-of-concept)  
6. Your environment (OS, architecture, version)

We will **never** request sensitive information, private keys, or wallets.

---

## Coordinated Disclosure

We follow a standard *coordinated disclosure process*:

1. Acknowledge the report within 48–72h  
2. Assess severity  
3. Prepare a fix  
4. Issue a patched release  
5. Public disclosure after patch → researcher is optionally credited

---

## Hall of Fame (future)

Valid security researchers may be listed in a future:

```
/docs/HALL_OF_FAME.md
```

The page is currently empty, but prepared for future contributions.

---

## Integrity & Verification

All releases must be verified before execution.

See:  
✔ **[`VERIFYING_DOWNLOADS.md`](VERIFYING_DOWNLOADS.md)**  
✔ **[`docs/KEYS/DARKNODE_BUILD.asc`](docs/KEYS/DARKNODE_BUILD.asc)**  
✔ **[`TRUST_MODEL.md`](TRUST_MODEL.md)**

---

## Scope

Reports we *do* accept:

- Remote code execution  
- Sandbox escapes  
- Signature / integrity bypass  
- Supply chain vulnerabilities  
- Privilege escalation  
- Verification flaws  
- Network protocol vulnerabilities  
- Dangerous default configurations  

Reports we *do not* accept:

- Social engineering  
- Self-inflicted misconfiguration  
- Outdated OS / malware on operator systems  
- Non-security bugs  
- Requests for private financial information

---

## Final Notes

Thank you for helping secure Darknode.  
Distributed compute networks rely on strong, transparent and open security processes.

