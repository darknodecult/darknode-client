# darknode-client

Decentralized compute client for the Darknode ecosystem.  
Deterministic local execution, secure task handling and operator-side infrastructure layer.

**Status:** Early preview / under active development.  
**Target users:** Home operators, VPS providers and small data centers who want to contribute compute capacity to the Darknode / DARE / DRE / AIGO stack.

---

## Goals

- Provide a **transparent, auditable client** for the Darknode network  
- Make it easy for **home and VPS operators** to contribute compute  
- Focus on **deterministic workloads**, **clear resource limits**, and **security-first defaults**  
- Offer a clean separation between:
  - **Operator layer** (this client)
  - **Orchestration protocol** (DARE)
  - **Runtime & rewards layer** (DRE)
  - **Optimization layer** (AIGO)

---

## Repository Structure

The repository will gradually evolve. Planned structure:

```
/docs/                    → Client usage docs, CLI commands, SECURITY, TRUST_MODEL  
/docs/VERIFYING...       → How to verify binaries / releases  
/docs/KEYS/              → Public keys for signature verification  
/src/                    → Client source code  
/build/                  → Build artifacts (local only)
```

---

## Release Integrity

Before running any downloaded release, verify:

- ✔ SHA-256 checksum  
- ✔ GPG signature  
- ✔ Matching fingerprint from this repository  
- ✔ (Future) reproducible build metadata  

Full verification guide:  
➡️ **[`VERIFYING_DOWNLOADS.md`](docs/VERIFYING_DOWNLOADS.md)**

Official build key:  
➡️ **[`docs/KEYS/DARKNODE_BUILD.asc`](docs/KEYS/DARKNODE_BUILD.asc)**

---

## Trust Model

Darknode Client follows a strict **zero-blind-trust** security philosophy:

- Operators must NOT blindly trust the network  
- The network must NOT blindly trust operators  
- All workloads must run deterministically  
- Sandboxed execution is mandatory  
- Verification always happens locally first

Full trust definition:  
➡️ **[`TRUST_MODEL.md`](docs/TRUST_MODEL.md)**

---

## Security

Security researchers are welcome and encouraged to submit responsible disclosures.

See full policy:  
➡️ **[`SECURITY.md`](SECURITY.md)**

Contact:
- 📧 security@darknode.tech  
- 🔐 GitHub Security Advisories (preferred)

Valid vulnerabilities *may* be credited in a future Hall of Fame.

---

## Build Instructions (placeholder)

Build steps depend on the final architecture (Node.js or Rust-based).  
Full reproducible build instructions will be added when the first preview build is published.

**Planned distribution channels:**

- Prebuilt binaries for Windows / Linux  
- Checksums + signatures for each release  
- Reproducible build metadata (future)  
- Package managers (winget / apt / brew; future)

---

## License

Released under the **MIT License**.  
See [`LICENSE`](LICENSE).

---
