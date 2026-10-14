---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
        "Two-factor authentication"
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

# Only its holder turns two-factor authentication on, and only its holder or a Sysadmin turns it off

Two-factor authentication is each person's own setting; a Sysadmin can turn it off for someone who lost their device.
