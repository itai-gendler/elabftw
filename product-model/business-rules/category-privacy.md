---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "category",
      "effect": "changes",
      "facts": [
        "Private"
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "keeps",
          "entity": "team"
        },
        {
          "verb": "has",
          "entity": "team-membership"
        },
        {
          "verb": "holds",
          "entity": "user"
        }
      ],
      "when": [
        {
          "entity": "team-membership",
          "fact": "Role",
          "is": "Admin"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractStatus.php"
    }
  ]
}
---

# Only an Admin of its team changes whether a category is private

Whether a category stays within its team is the team Admin's decision. New categories are private.
