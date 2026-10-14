---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "status",
      "effect": "changes",
      "to": "Deleted"
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
          "fact": "Applies to",
          "is": "Experiments"
        },
        {
          "entity": "team",
          "fact": "Allow users to create and edit experiment status",
          "is": "On"
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
          "fact": "Applies to",
          "is": "Resources"
        },
        {
          "entity": "team",
          "fact": "Allow users to create and edit resources status",
          "is": "On"
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
      "target": "src/Models/AbstractStatus.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractCategory.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/sql/structure.sql"
    }
  ]
}
---

# Members delete a status while their team lets them; Admins always may

Deleting a status follows the same team setting as creating one.
