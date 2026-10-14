---
{
  "domain": "settings",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/SigKeys.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/SignatureHelper.php"
    }
  ]
}
---

# Signature key pair

A person's Ed25519 key pair for cryptographic signatures; the private key is protected by a passphrase only its holder knows.

## Information kept

- **Public key** — the key anyone can use to verify a signature
- **Private key** — the passphrase-protected key that signs
- **Last used at** — when it last signed

## States

### Active

The key the person signs with.

### Archived

Replaced by a newer key pair and no longer used to sign.
