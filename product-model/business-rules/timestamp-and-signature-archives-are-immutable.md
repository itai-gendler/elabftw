---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "timestamp-entry"
    },
    {
      "type": "capability",
      "id": "sign-entry"
    },
    {
      "type": "capability",
      "id": "delete-file"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Uploads.php"
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

# Timestamp and signature archives are never edited, replaced or deleted on their own

The archive a timestamp or a signature attaches, and the comment a signature adds, stay as made. The archives are kept among the entry's archived files.
