---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "status",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/templates/categories-status-index.macro.html"
    }
  ]
}
---

# Only an Admin of its team changes whether a status is private

Whether a status stays within its team or is offered to other teams is the team Admin's decision, even where members may otherwise edit statuses. New statuses are private.
