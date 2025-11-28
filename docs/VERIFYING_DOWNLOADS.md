# 🔐 Verifying Darknode Downloads

All official Darknode releases must be verified **before execution**.  
This ensures that the downloaded file:

- ⚡ is authentic (signed by the Darknode Build System)  
- 🛡 has not been tampered with  
- 📦 matches the official SHA256 checksum  

These protections are critical for operating secure distributed compute nodes.

---

# 1. Download the Release

Official builds are released at:

👉 https://github.com/darknode-tech/darknode-client/releases

Each release contains files such as:

```
darknode-client-<version>-linux.tar.gz
darknode-client-<version>-linux.tar.gz.sha256
darknode-client-<version>-linux.tar.gz.sig
```

---

# 2. Verify the SHA256 Checksum

This step ensures the file was not corrupted or altered.

## Linux / macOS:

```sh
sha256sum darknode-client-<version>-linux.tar.gz
cat darknode-client-<version>-linux.tar.gz.sha256
```

## Windows (PowerShell):

```powershell
Get-FileHash .\darknode-client-<version>-windows.zip -Algorithm SHA256
Get-Content .\darknode-client-<version>-windows.zip.sha256
```

### ✔ Expected Result:

- Hashes **must match exactly**
- If they differ: **STOP — do NOT run the file**

---

# 3. Import the Darknode Build System Public Key

Fingerprint:

```
D5B4 67C1 4447 AC02 A76E  BC77 52A3 8DDA 6F8D 664F
```

Public key download:

```
https://github.com/darknode-tech/darknode-client/blob/main/docs/KEYS/DARKNODE_BUILD.asc
```

## Linux / macOS:

```sh
gpg --import DARKNODE_BUILD.asc
```

## Windows (PowerShell):

```powershell
gpg --import .\DARKNODE_BUILD.asc
```

---

# 4. Verify the GPG Signature

## Linux / macOS:

```sh
gpg --verify darknode-client-<version>-linux.tar.gz.sig \
            darknode-client-<version>-linux.tar.gz
```

## Windows (PowerShell):

```powershell
gpg --verify .\darknode-client-<version>-windows.zip.sig `
             .\darknode-client-<version>-windows.zip
```

### ✔ Expected:

```
Good signature from "Darknode Build System <security@darknode.tech>"
Primary key fingerprint: D5B4 67C1 4447 AC02 A76E  BC77 52A3 8DDA 6F8D 664F
```

### ✘ Invalid signature?

STOP — Do not run the file.  
Re-download from the official Releases page.

---

# 5. Optional: Verify File Metadata

(For advanced users)

```sh
file darknode-client-<version>-linux.tar.gz
```

Expected:

```
gzip compressed data
```

---

# 6. Reproducible Build Verification (future)

Future versions will support:

- deterministic builds  
- reproducible compilation  
- matching SHA256 hashes across builders  
- cross-platform determinism  

A standardized `verify-build.sh` script will be provided later.

---

# 7. Troubleshooting

### ❌ "No public key found"
You did not import the public key.  
Run:

```sh
gpg --import DARKNODE_BUILD.asc
```

### ❌ "BAD SIGNATURE"
Do **NOT** run the file — it is corrupted or tampered with.

### ❌ "gpg: verify failed"
Make sure both files are passed:

- `.sig`
- and the binary itself

---

# 8. Support

If verification fails or you have questions, contact:

📬 `security@darknode.tech`  
🔐 Encrypted reports preferred.

---

# 🔏 Always verify before running Darknode.
Security is a core requirement of distributed compute networks.
