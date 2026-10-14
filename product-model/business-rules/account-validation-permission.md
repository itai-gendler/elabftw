---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
        "Validated",
        "Valid until"
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "uses",
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
      "target": "src/Models/Users/Users.php"
    }
  ]
}
---

# Only an Admin of a team the person belongs to, or a Sysadmin, validates an account or sets its validity date

Validating lets a registered person sign in. Admins validate people who belong to one of their teams; Sysadmins validate anyone.
