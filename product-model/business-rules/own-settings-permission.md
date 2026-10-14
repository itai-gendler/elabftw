---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
        "Preferred language",
        "Markdown editor",
        "Default visibility",
        "Default write permission",
        "Pinned entries",
        "Notification preferences"
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "uses",
          "entity": "user"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Users/Users.php"
    }
  ]
}
---

# Only its holder changes an account's general settings

Language, editor and default permissions are each person's own.
