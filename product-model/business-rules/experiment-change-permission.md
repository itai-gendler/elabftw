---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "experiment",
      "effect": "changes",
      "facts": [
        "Title",
        "Date",
        "Main text",
        "Custom ID",
        "Category",
        "Status",
        "Tags",
        "Custom fields",
        "Visibility",
        "Can write",
        "Locked",
        "Owner",
        "Team",
        "Last changed by",
        "Linked entries",
        "Compounds",
        "Share link"
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
        },
        {
          "fact": "Locked",
          "is": "No"
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
        },
        {
          "fact": "Locked",
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
          "fact": "Can write",
          "is": "Only members of the team"
        },
        {
          "fact": "Locked",
          "is": "No"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "user"
        }
      ],
      "when": [
        {
          "fact": "Locked",
          "is": "No"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "locks",
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

# Only people its write permission admits change an experiment

An experiment is changed by its owner and by whoever its Can write setting admits, on the same levels as Visibility, with an Admin of its team admitted at every level but “Only owner”. While it is locked, only the person who locked it and Admins may change it.

## Rationale

Locking is how the lab notebook freezes a record without deleting it, so a lock binds everyone but its author and the team's Admins.
