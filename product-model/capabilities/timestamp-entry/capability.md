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
      "target": "src/Make/AbstractMakeTimestamp.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Make/AbstractMakeTrustedTimestamp.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Make/MakeBloxberg.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractConcreteEntity.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/ts/toolbar.ts"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/traceability-and-auditability.md"
    }
  ]
}
---

# Timestamp an entry

Make legal proof that an entry's data existed at a point in time. The Product exports the entry, has the export's fingerprint certified by a trusted Time Stamping Authority (RFC 3161) or, where enabled, by the Bloxberg blockchain, and attaches data and proof as an immutable archive. Reading the entry is enough to timestamp it, and the entry stays editable afterwards.
