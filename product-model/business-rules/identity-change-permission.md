---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
        "Name",
        "Email",
        "ORCID"
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "uses",
          "entity": "user"
        }
      ],
      "when": [
        {
          "entity": "instance-settings",
          "fact": "Allow users to change identity",
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
      "target": "src/Models/Users/Users.php"
    }
  ]
}
---

# People change their own name, email or ORCID while the instance allows it; Sysadmins always may

With “Allow users to change identity” off, only a Sysadmin changes a person's name, email or internal id.
