---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "team-membership",
      "effect": "changes",
      "facts": [
        "Role"
      ]
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

# Only an Admin of the team or a Sysadmin changes a member's role

Admins of a team, and Sysadmins, make members Admins or Users of that team.
