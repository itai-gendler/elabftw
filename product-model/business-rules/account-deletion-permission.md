---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "removes"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/UsersHelper.php"
    }
  ]
}
---

# Only an Admin of a team the person belongs to, or a Sysadmin, deletes an account, and only one that owns nothing

An account that owns experiments, resources, comments, templates or files is never deleted; archiving is the way to stop its use.
