---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "experiment",
      "effect": "changes",
      "facts": [
        "Timestamped",
        "Timestamped at",
        "Signature count",
        "Last signed at"
      ]
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
      "target": "src/Models/AbstractEntity.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Uploads.php"
    }
  ]
}
---

# Anyone who can read a experiment timestamps or signs it

Timestamping and signing record facts about a experiment without changing its content, so read access is enough: a reader without write access, even on a locked experiment, can timestamp or sign it.
