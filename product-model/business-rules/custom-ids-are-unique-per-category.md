---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "get-next-custom-id"
    },
    {
      "type": "capability",
      "id": "create-entry"
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
      "target": "src/Models/AbstractConcreteEntity.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/sql/structure.sql"
    }
  ]
}
---

# A Custom ID is used once per category

Two entries of the same category never share a Custom ID; setting one already in use is refused, and the next Custom ID is the highest in the category plus one.
