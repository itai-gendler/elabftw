---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "api-key",
      "effect": "removes"
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "holds",
          "entity": "user"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "holds",
          "entity": "user"
        },
        {
          "verb": "holds",
          "entity": "team-membership"
        },
        {
          "verb": "has",
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
    },
    {
      "actors": [
        "sysadmin"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/ApiKeys.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Users2Teams.php"
    }
  ]
}
---

# Only its holder deletes an API key

People revoke their own API keys. Removing or archiving someone in a team also revokes their keys bound to that team.
