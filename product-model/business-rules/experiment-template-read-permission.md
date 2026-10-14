---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "experiment-template",
      "effect": "reads"
    }
  ],
  "permits": [
    {
      "actors": [
        "visitor"
      ],
      "when": [
        {
          "fact": "Visibility",
          "is": "Everyone including anonymous users"
        },
        {
          "entity": "instance-settings",
          "fact": "Anonymous visitors",
          "is": "Allowed"
        }
      ]
    },
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "fact": "Visibility",
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
          "fact": "Visibility",
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
          "fact": "Visibility",
          "is": "Only members of the team"
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
          "fact": "Visibility",
          "is": "Only owner and admins"
        },
        {
          "entity": "team-membership",
          "fact": "Role",
          "is": "Admin"
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
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Elabftw/Permissions.php"
    }
  ]
}
---

# Only people its visibility admits read or use an experiment template

An experiment template is read, and used to create entries, by its owner and whoever its Visibility admits, on the same levels as an entry.
