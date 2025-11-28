# Contributing to darknode-client

Thank you for your interest in contributing!  
This document describes how to report issues, submit pull requests, and follow the security and development guidelines for the **darknode-client** project.

Darknode Client is in **early development**, and contributions are welcome — especially for security auditing, code improvements, documentation, and packaging.

---

## 1. Before You Start

Please ensure you have read:

- **README.md** — project overview & goals  
- **SECURITY.md** — vulnerability reporting  
- **TRUST_MODEL.md** — trust boundaries, architecture assumptions  
- **VERIFYING_DOWNLOADS.md** — file verification  
- **Code of Conduct** (below)

Following these ensures aligned contributions and reduces friction in code review.

---

## 2. How to Contribute

### ✔ Report issues
Submit issues here:  
https://github.com/darknodecult/darknode-client/issues

Include:

- Clear title  
- Steps to reproduce  
- Expected vs. actual behavior  
- Environment details (OS, version, logs)  
- Security-related issues → **do NOT open an issue** (see SECURITY.md)

---

### ✔ Submit Pull Requests

1. Fork the repository  
2. Create a feature branch  
3. Follow coding conventions  
4. Ensure your PR:
   - is focused (one change per PR)
   - includes tests (once test framework is added)
   - includes documentation updates if applicable
5. Make sure `npm run lint` or `cargo fmt` (TBD) passes  
6. Submit PR with a clear explanation of:
   - What problem it solves  
   - Why this approach  
   - Any trade-offs  

PRs that modify core security logic will receive extra review.

---

## 3. Development Requirements

Current tooling (may evolve):

- Git  
- Node.js or Rust (depending on final architecture)  
- Linux or WSL recommended  
- GPG (optional, for commit signing)  

### Development Setup (placeholder)

```
git clone https://github.com/darknodecult/darknode-client.git
cd darknode-client
npm install   # or "cargo build" (TBD)
```

Full setup will be documented once early builds stabilize.

---

## 4. Code of Conduct

Contributors must:

- Communicate respectfully  
- Keep discussions constructive  
- Avoid toxic or hostile behavior  
- Follow all security guidelines  

Toxic behavior can lead to blocked PRs or access removal.

---

## 5. Issue Reporting Rules

Before submitting:

- Check existing issues  
- Provide reproduction steps  
- Include OS, logs, environment  
- Describe expected vs. actual behavior  

Report issues related to:

- Bugs  
- Unexpected behavior  
- Documentation gaps  
- Performance problems  
- Build errors  

Do **NOT** file issues for:

- Security vulnerabilities (see SECURITY.md)  
- Support for unofficial forks  
- Private builds  
- Speculation or unrelated questions

---

## 6. Commit Hygiene

Follow these simple rules:

- Write meaningful commit messages  
- Keep commits atomic  
- Use conventional prefixes when possible:
  - `fix:` bug fix
  - `feat:` new feature
  - `docs:` documentation
  - `refactor:` code restructuring
  - `chore:` non-functional change  
- Avoid committing generated files or secrets

Signed commits via GPG are optional but encouraged.

---

## 7. Branch Naming

Recommended:

- `feature/<feature-name>`
- `fix/<bug-name>`
- `docs/<topic>`
- `security/<patch>`

Avoid vague names like `update`, `test`, `stuff`, `tmp`.

---

## 8. Style Guidelines

(TBD once language ecosystem is finalized)

Planned:

- Prettier/ESLint or Rustfmt/Clippy  
- Strict typing rules (TS or Rust)  
- No console.log spam  
- Clear error boundaries  
- No silent failures  

---

## 9. Testing

Full testing pipeline will be added in later builds.  
Contributions may include:

- Unit tests  
- Integration tests  
- Security regression tests  

---

## 10. Security Best Practices for Contributors

- Never bypass validation layers  
- Never reduce sandbox or isolation guarantees  
- Avoid introducing implicit trust paths  
- Keep dependencies minimal  
- Prefer deterministic, explicit behavior over magic/automation  

If unsure → ask in the PR notes.

---

## 11. Responsible Disclosure (Security)

Security vulnerabilities must be reported privately via:

📧 **security@darknode.tech**  
🔐 PGP key: *TBA (to be published before first binary release)*

Do **not** open a public issue for security concerns.

Valid reports may be credited in the future **Hall of Fame**.

---

## 12. Contributor Recognition

Contributors may be recognized for:

- Code contributions  
- Security disclosures  
- Documentation work  
- Tooling improvements  

A contributor list will be added once the project grows.

---

## 13. License

By contributing, you agree your code is submitted under the **MIT License**, same as the repository.

---

## 14. Final Notes

The project is still stabilizing.  
Thanks for helping build a transparent, secure, operator-controlled compute client for the Darknode ecosystem.

If you have questions → open an issue or discuss inside the PR.  
Your contributions are highly valued.

