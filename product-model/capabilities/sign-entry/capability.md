---
{
  "availability": [
    {
      "place": "web::signed-in"
    },
    {
      "place": "api"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractEntity.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/SignatureHelper.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/ImmutableComments.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/traceability-and-auditability.md"
    }
  ]
}
---

# Sign an entry

Cryptographically sign an experiment or resource to show that this data was approved by this person, with a stated meaning such as Review or Approval. Reading the entry is enough to sign it.
