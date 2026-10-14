---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "to-do-item",
      "effect": "changes"
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "keeps",
          "entity": "user"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Todolist.php"
    }
  ]
}
---

# Only its owner edits a to-do item

A to-do list is private to the person who keeps it.
