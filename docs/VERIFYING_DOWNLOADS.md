# Verifying Darknode Client Downloads

This guide explains how to verify the authenticity and integrity of all Darknode Client releases. Every release is published with:

- SHA-256 checksums  
- A cryptographic GPG signature  
- Metadata for reproducible builds (future)

These steps ensure your executable has not been tampered with and really comes from the official Darknode build system.

---

## 1. Download the Release

Get the latest preview build:

https://github.com/darknodecult/darknode-client/releases

Each release contains files like:

darknode-client-<version>-linux.tar.gz  
darknode-client-<version>-linux.tar.gz.sha256  
darknode-client-<version>-linux.tar.gz.sig  

---

## 2. Verify the SHA256 Checksum

Run:

sha256sum darknode-client-<version>-linux.tar.gz

Compare with:

cat darknode-client-<version>-linux.tar.gz.sha256

Expected result:

✔ Hashes match → file integrity OK  
✖ Mismatch → file corrupted/tampered → STOP — do not run it

---

## 3. Import the Official Darknode Build Key

(Real key will be added later.)

gpg --keyserver keyserver.ubuntu.com --recv-keys <PGP_KEY_ID>

Verify:

gpg --fingerprint <PGP_KEY_ID>

Ensure it matches the fingerprint in SECURITY.md and on the Darknode website.

---

## 4. Verify the GPG Signature

gpg --verify darknode-client-<version>-linux.tar.gz.sig darknode-client-<version>-linux.tar.gz

Expected output:

Good signature from "Darknode Build System <security@darknode.tech>"

✔ Valid signature → file is authentic  
✖ Invalid → do not trust the file

---

## 5. Optional: Verify File Metadata

file darknode-client-<version>-linux.tar.gz

Expected:

gzip compressed data

---

## 6. Reproducible Build Verification (Future)

Future versions will support:

- deterministic builds  
- reproducible compilation  
- identical SHA256 hashes  

This allows anyone to confirm that the binary matches the source code.

More info will be added in:

docs/REPRODUCIBLE_BUILDS.md

---

## 7. If Verification Fails

If any check fails:

- checksum mismatch  
- invalid signature  
- unknown fingerprint  
- unexpected metadata  

STOP immediately. Do NOT run the file.

Report issues:

security@darknode.tech  
https://github.com/darknodecult/darknode-client/security/advisories

---

## 8. Disclaimer

The Darknode Client is early preview. Verification procedures may evolve.

Thank you for helping to secure the Darknode ecosystem.
