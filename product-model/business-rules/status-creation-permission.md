---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "status",
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

# Members create a status while their team lets them; Admins always may

Any member may add an experiment or resource status while the team's matching “Allow users to create and edit … status” setting is on, as it is for every new team; turning it off keeps statuses for the team's Admins.
