---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "experiment-template",
      "effect": "changes",
      "facts": [
        "Title",
        "Main text",
        "Category",
        "Status",
        "Tags",
        "Custom fields",
        "Visibility",
        "Can write",
        "Entry visibility",
        "Entry write permission",
        "Lock down read permissions",
        "Lock down write permissions"
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
      "target": "src/Elabftw/Permissions.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractEntity.php"
    }
  ]
}
---

# Only people its write permission admits change an experiment template

An experiment template is changed by its owner and whoever its Can write setting admits; changes apply to entries created afterwards, never to existing ones.
