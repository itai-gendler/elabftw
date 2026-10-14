---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "experiment",
      "effect": "changes",
      "facts": [
        "Can write"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "fact": "Can write locked down",
          "is": "No"
        }
      ]
    },
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
      "target": "src/Models/AbstractEntity.php"
    }
  ]
}
---

# Only an Admin changes who can write an experiment whose write permission is locked down

A template can lock down the Can write setting of the entries created from it; on such an experiment, members cannot change it and Admins still can.
