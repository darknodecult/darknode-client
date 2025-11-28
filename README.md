# darknode-client

Decentralized compute client for the Darknode ecosystem.  
Deterministic local execution, secure task handling and operator-side infrastructure layer.

> **Status:** Early preview / under active development.  
> **Target users:** Home operators, VPS providers and small data centers who want to contribute compute capacity to the Darknode / DARE / DRE / AIGO stack.

---

## Goals

- Provide a **transparent, auditable client** for the Darknode network.
- Make it easy for **home and VPS operators** to connect their hardware.
- Focus on **deterministic workloads**, **clear resource limits** and **security-first defaults**.
- Offer a clean separation between:
  - **Operator layer** (this client)
  - **Orchestration protocol** (DARE)
  - **Runtime & rewards layer** (DRE)
  - **Optimization layer** (AIGO)

---

## Repository Structure

This repository will gradually evolve. Planned structure:

- `src/` – Client source code (daemon, CLI, UI components, etc.)
- `docs/` – Documentation, security notes and trust model.
  - `docs/VERIFYING_DOWNLOADS.md` – How to verify binaries / releases.
  - `docs/TRUST_MODEL.md` – High-level architecture & security assumptions (WIP).
- `.github/SECURITY.md` – How to report vulnerabilities.
- `CONTRIBUTING.md` – How to contribute, open issues or suggest improvements.

---

## Installation (placeholder)

> ⚠️ **Work in progress.**  
> Installation instructions will be added when the first public preview build is available.

Planned distribution channels:

- **Prebuilt binaries** for Windows / Linux.
- **Checksums + signatures** for each release (see [`docs/VERIFYING_DOWNLOADS.md`](docs/VERIFYING_DOWNLOADS.md)).
- Optionally a **Docker image** and package manager integration.

---

## Security & Verification

Security is a first-class concern for the Darknode client.

- Every public release will ship with:
  - SHA-256 checksum files
  - (Optional) detached signatures
- Users will be able to verify downloads using standard tools before execution.
- We maintain a dedicated **security policy** and a contact for security researchers.

👉 See:

- [`docs/VERIFYING_DOWNLOADS.md`](docs/VERIFYING_DOWNLOADS.md)
- [`.github/SECURITY.md`](.github/SECURITY.md)

---

## For Operators

The client is designed for:

- Home servers and small form factor machines
- VPS instances
- Edge nodes

Planned features include:

- Resource limits (CPU, RAM, disk)
- Clear visibility into which workloads are being executed
- Logs and metrics suitable for monitoring and auditing
- A simple **opt-in / opt-out** model for different workload types (AI, rendering, zk, etc.)

---

## Contributing

Contributions are welcome once the basic protocol and client internals have stabilized.

- Please read [`CONTRIBUTING.md`](CONTRIBUTING.md) before opening a PR.
- For security-sensitive topics, **do not** open a public issue.
  - Instead, follow the process in [`.github/SECURITY.md`](.github/SECURITY.md).

---

## License

This project is licensed under the **MIT License**.  
See the `LICENSE` file for details.
