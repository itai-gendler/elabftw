---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
        "Password"
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
    }
  ]
}
---

# Only its holder, knowing the current password or holding an emailed reset link, or a Sysadmin changes an account's password

People change their own password after confirming the current one, or, signed out, through a reset link emailed to the account's address and valid for 15 minutes; a Sysadmin may set anyone's.
