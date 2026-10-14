---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "team",
      "effect": "changes"
    }
  ],
  "permits": [
    {
      "related": [
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
      "target": "src/Models/Teams.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/admin.php"
    }
  ]
}
---

# Only an Admin of the team or a Sysadmin changes its settings

A team's settings, including what its members may create and whether templates are forced, are changed by its Admins and by Sysadmins.
