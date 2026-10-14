---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "category",
      "effect": "creates"
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
          "fact": "Allow users to create and edit experiments categories",
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
          "fact": "Allow users to create and edit resources categories",
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

# Members create a category while their team lets them; Admins always may

Any member may manage the team's experiment or resource categories while the matching “Allow users to create and edit … categories” setting is on, as it is for every new team; turning it off keeps categories for the team's Admins.
