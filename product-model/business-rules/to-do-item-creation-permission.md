---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "to-do-item",
      "effect": "creates"
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

# Only its owner adds to a to-do list

A to-do list is private to the person who keeps it.
