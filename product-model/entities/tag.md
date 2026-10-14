---
{
  "domain": "admin-panel",
  "relations": [
    {
      "entity": "experiment",
      "verb": "marks",
      "cardinality": "many-to-many"
    },
    {
      "entity": "resource",
      "verb": "marks",
      "cardinality": "many-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/TeamTags.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Tags.php"
    }
  ]
}
---

# Tag

A team-wide label that groups entries across categories; the same tag can be attached to many experiments and resources.

## Information kept

- **Name** — the label text, unique within the team
