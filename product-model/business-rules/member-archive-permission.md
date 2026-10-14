---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "team-membership",
      "effect": "changes",
      "to": "Archived"
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
          "fact": "Allow Admins to archive users",
          "is": "On"
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
      "target": "src/Services/UserArchiver.php"
    }
  ]
}
---

# Only an Admin of the team, while the instance allows it, or a Sysadmin archives a member

Team Admins archive members of their team only while the instance's “Allow Admins to archive users” setting is on; Sysadmins always may. Sysadmin accounts and unvalidated accounts are never archived.
