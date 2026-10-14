---
{
  "availability": [
    {
      "place": "web::signed-in"
    }
  ],
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
      "target": "src/templates/ucp.html"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/traceability-and-auditability.md"
    }
  ]
}
---

# Generate signature keys

Create one's own signature key pair, protected by a passphrase, or regenerate it; regenerating archives the current pair.
