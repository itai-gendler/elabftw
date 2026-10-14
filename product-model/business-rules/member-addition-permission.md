---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "team-membership",
      "effect": "creates"
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
        },
        {
          "entity": "instance-settings",
          "fact": "Allow Admins to add existing users to their team",
          "is": "On"
        }
      ]
    },
    {
      "actors": [
        "sysadmin"
      ]
    },
    {
      "actors": [
        "visitor"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Users/Users.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Users2Teams.php"
    }
  ]
}
---

# Only an Admin of the team, while the instance allows it, or a Sysadmin adds an existing person to a team

Team Admins add people who already have an account only while the instance's “Allow Admins to add existing users to their team” setting is on, which it is not by default; Sysadmins always may. Registration adds the registering person to the team they chose.
