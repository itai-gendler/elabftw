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
      "target": "src/Models/Experiments.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/ts/toolbar.ts"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/user-guide/experiments.md"
    }
  ]
}
---

# Duplicate an entry

Create a copy of an experiment or resource to start a new iteration. Reading the original is enough, but the copy counts as a new entry, so the team's creation settings apply.
