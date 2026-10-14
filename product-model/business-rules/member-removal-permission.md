---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "team-membership",
      "effect": "removes"
    }
  ],
  "permits": [
    {
      "related": [
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
      "target": "src/Models/Users2Teams.php"
    }
  ]
}
---

# Only an Admin of the team or a Sysadmin removes a member, who keeps at least one team

Admins of a team, and Sysadmins, remove people from it, never from their last team.
