---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "experiment",
      "effect": "creates"
    },
    {
      "type": "entity",
      "id": "experiment",
      "effect": "changes"
    },
    {
      "type": "entity",
      "id": "resource",
      "effect": "creates"
    },
    {
      "type": "entity",
      "id": "resource",
      "effect": "changes"
    },
    {
      "type": "entity",
      "id": "changelog-entry"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Changelog.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractEntity.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/traceability-and-auditability.md"
    }
  ]
}
---

# Every change to an experiment or resource is recorded in its changelog

Creation, with the template or entry it came from, and every later change, from fields and permissions to locks, steps, tags, timestamps, signatures and requests, adds a changelog entry naming who made it. Changes to the main text point to the revisions.
