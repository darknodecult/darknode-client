# Darknode Client – Trust Model

The Darknode Client is designed as a deterministic, security-first execution layer 
running on machines owned by operators (home users, VPS providers, small data centers).  
This document defines **what must be trusted**, **what must not be trusted**, and 
the **boundary assumptions** for safe operation.

It is intended for:

- Security researchers  
- Operators running the client  
- Auditor teams  
- Developers working on protocol layers (DARE, DRE, AIGO)  

---

# 1. System Overview

The Darknode ecosystem consists of four main layers:

1. **DARKNODE — Operator & infrastructure layer (this client)**  
2. **DARE — Deterministic compute protocol**  
3. **DRE — Distributed runtime engine**  
4. **AIGO — Optimization & AI-driven routing layer**

The client sits at **Layer 1** and provides the execution environment, 
resource limits, sandboxing and local security guarantees.

---

# 2. Threat Model Summary

The Darknode Client assumes:

- The operator’s machine may run **untrusted workloads**, but inside a sandbox.
- The orchestrator (DARE/AIGO) may send **malicious tasks**, intentionally or due to compromise.
- Network traffic may be intercepted, altered or replayed.
- Operators may misconfigure the client unintentionally.
- Attackers may attempt to escape workload isolation or exploit the client process.

The client is responsible for:

- Protecting the operator’s machine from remote tasks  
- Protecting the integrity of executed workloads  
- Authenticating update and control messages  
- Never running anything that was not explicitly validated  

---

# 3. Trust Assumptions (What You *Must* Trust)

Operators and auditors must trust the following components:

### ✔ The binary / package you download  
It must be the official build from our GitHub Releases.  
(See `docs/VERIFYING_DOWNLOADS.md` for verification.)

### ✔ The sandboxing layer  
Local execution is restricted through deterministic limits:

- CPU
- Memory
- Timeouts
- File system access  
- Network policies (WIP)

### ✔ The local configuration  
The configuration file defines:

- allowed workload types  
- resource ceilings  
- logging preferences  

If misconfigured, the client may behave unexpectedly.

### ✔ The host operating system  
No sandbox can be stronger than the underlying OS.

---

# 4. Non-Trust Assumptions (What You *Do Not* Have to Trust)

To increase safety, the operator does **not** have to trust:

### ❌ Remote tasks  
Workloads are treated as untrusted code/data and fully sandboxed.

### ❌ The orchestrator (DARE/AIGO)  
The client assumes:

- orchestration may be compromised  
- routing decisions may be manipulated  
- tasks may be malformed or malicious  

The client still must remain safe.

### ❌ Other nodes in the network  
Other Darknode operators may be hostile or compromised.

### ❌ Network infrastructure  
MITM, packet modification, replay and traffic inspection are assumed possible.

---

# 5. Security Boundaries

The trust boundary is defined around the **local client runtime**.

Everything outside of it is untrusted:

    +-------------------------------------------+
    |             Operator Machine              |
    |   (trusted OS, trusted config, trusted    |
    |      Darknode Client binary)              |
    +----------------------^--------------------+
                           |
            Trust boundary |  Everything below is untrusted
                           |
    +----------------------v--------------------+
    |      Tasks, Orchestrator, Network         |
    |    DARE/AIGO messages, remote requests    |
    +-------------------------------------------+

---

# 6. Attack Vectors Considered In-Scope

The Darknode Client protects against:

### 6.1 Malicious Tasks
- Arbitrary code execution attempts  
- VM escape attempts  
- Excessive resource usage  
- File system probing  
- Privilege escalation attempts  

### 6.2 Malicious Orchestrator Messages
- Task injection  
- Manipulated payloads  
- Invalid signatures  
- Corrupted compute jobs  

### 6.3 Hostile Network Conditions
- MITM  
- Replay attacks  
- Packet tampering  
- Downgrade attempts  

### 6.4 Local Misconfigurations
- Unsafe defaults  
- Running unintended workload types  
- Excessive permissions  

---

# 7. Attack Vectors Out-of-Scope

The client does **not** protect against:

### ✖ Physical access to the machine  
### ✖ Compromised host OS  
### ✖ Broken hardware or firmware  
### ✖ Extreme kernel-level exploits (out of practical scope)  
### ✖ Attacks requiring root access  
### ✖ Social engineering  

These are outside the realistic capability of a user-space client.

---

# 8. Security Guarantees

The Darknode Client aims to guarantee:

### ✔ Deterministic execution  
Two identical inputs produce identical results.

### ✔ Sandboxed workloads  
Tasks cannot access host OS or operator files.

### ✔ Predictable resource limits  
CPU, RAM, disk and network budgets enforced.

### ✔ Signed updates and releases  
No unsigned update will be accepted.

### ✔ Transparent logs  
Operators can see **exactly** what is happening.

---

# 9. Security Limitations

No system is perfect. Current limitations include:

- No hardware-backed isolation (yet)  
- No automatic attestation  
- No distributed reputation system  
- Sandboxing depends on OS security model  
- Running workloads still increases attack surface  

Future versions will address these.

---

# 10. Future Security Enhancements

Planned improvements:

### 🔐 Hardware-backed isolation (TPM / SGX / SEV)
Enables verifiable, tamper-resistant execution.

### 📡 Secure remote attestation
Operators can prove:

- correct binary  
- correct config  
- correct sandbox state  

### 🛡 Reputation / slashing system
Rewards honest nodes, filters malicious ones.

### 🧪 Reproducible builds
Independent rebuilds → identical SHA-256 checksums.

### 🗄 Walled-off data volumes
Per-task encrypted scratch spaces.

---

# 11. Responsible Disclosure

Security researchers can report vulnerabilities using:

👉 `.github/SECURITY.md`  
👉 security@darknode.tech (placeholder)

Valid reports may be credited via the Hall of Fame.

---

# 12. Conclusion

This Trust Model makes explicit:

- What the operator must trust  
- What the operator must not trust  
- Which attack vectors are mitigated  
- Which ones are out-of-scope  

It forms the foundation of the Darknode Client’s security philosophy:  
**transparency, determinism, operator control, and zero blind trust.**

