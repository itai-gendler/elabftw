---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "experiment-template",
      "effect": "changes",
      "to": "Deleted"
    }
  ],
  "permits": [
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "fact": "Can write",
          "is": "Everyone including anonymous users"
        }
      ]
    },
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "fact": "Can write",
          "is": "Everyone with an account"
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
          "fact": "Can write",
          "is": "Only members of the team"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "user"
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
        },
        {
          "fact": "Can write",
          "is-not": "Only owner"
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

# Only people its write permission admits delete an experiment template

Deleting a template follows its Can write setting.
