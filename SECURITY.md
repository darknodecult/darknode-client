# 🔐 Darknode Security Policy

This document describes how to report vulnerabilities, how we handle responsible disclosure, and how to verify the integrity of Darknode software releases.

Darknode is committed to providing a secure environment for all home operators, developers, and enterprise users. Security researchers are highly encouraged to test, audit, and analyze our systems.

---

# 🛡️ 1. Reporting a Security Vulnerability

If you discover a vulnerability in any Darknode component (client, operator tools, API infrastructure, website, backend logic, or documentation), please report it responsibly and privately.

### 📬 **Primary Security Contact**
```
security@darknode.tech
```

### 🔑 PGP Public Key
Fingerprint (40 hex characters):

```
D5B4 67C1 4447 AC02 A76E  BC77 52A3 8DDA 6F8D 664F
```

Full ASCII-armored key:
```
https://github.com/darknode-tech/darknode-client/blob/main/docs/KEYS/DARKNODE_BUILD.asc
```

Please **encrypt all vulnerability reports** using the build system public key.

---

# 🧭 2. Scope of Responsible Disclosure

### In Scope:
- Darknode Client (Windows/Linux/macOS)
- Darknode Operator Layer
- DARE Execution Layer
- DRE Runtime Engine
- AIGO Optimization systems
- Darknode API endpoints
- darknode.tech + related web properties
- Release verification files (signatures/hashes)

### Out of Scope:
- Social engineering against community members
- Physical attacks on infrastructure you do not own
- Node misconfiguration caused by user modification
- 3rd-party software not maintained by Darknode
- Cloud infrastructure owned by hosting providers

---

# 🕒 3. Expected Response Timeline

- **Initial acknowledgement:** within **48 hours**
- **Triage & classification:** within **5 days**
- **Fix preparation:** depends on severity
- **Coordinated disclosure:** arranged individually

Critical vulnerabilities may receive accelerated handling.

---

# 🎁 4. Rewards / Bug Bounties

Darknode does not currently operate a monetary bug bounty program.  
However, high-value findings will receive:

- 🌟 **Hall of Fame listing**
- 🥇 Priority access to early releases
- 🔧 Direct communication channel with the core team

When funding becomes available, researchers who contributed early will be prioritized.

---

# 🔍 5. Verifying Darknode Releases

All official builds are signed by:

**Darknode Build System <security@darknode.tech>**

Use our verification guide for detailed instructions:

➡ **VERIFYING_DOWNLOADS.md**

Users MUST verify both:

1. SHA256 checksums  
2. GPG signatures

This ensures authenticity and integrity.

---

# ⚔️ 6. Coordinated Vulnerability Disclosure (CVD)

Darknode follows industry-standard CVD processes:

1. Researcher sends encrypted report.
2. We respond within the defined window.
3. Researcher and Darknode collaborate on patching.
4. Optional coordinated release date.
5. Public advisories may be published for severe issues.

We **never** pursue legal action against good-faith researchers.

---

# 🧑‍💻 7. Security Hall of Fame (reserved)

This section is reserved for future contributors who responsibly disclose verified security issues.

- (empty for now)

---

# 🧱 8. Trust Model Summary

Darknode uses:

- PGP-signed releases  
- Hash verification  
- Reproducible build plans (progressively rolled out)  
- Transparent open documentation  
- Minimal external dependencies  
- No telemetry in the home operator client  

For details see:

➡ `TRUST_MODEL.md`

---

# 🙏 Thank You

We deeply appreciate the work of security researchers, ethical hackers, and technical auditors who help secure decentralized systems.

If in doubt, always contact:

```
security@darknode.tech
```

Encrypted reports are strongly recommended.
