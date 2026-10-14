---
{
  "entities": [
    {
      "entity": "account",
      "collects": [
        "Password"
      ]
    }
  ],
  "entryPoints": [
    {
      "web": "/change-pass.php?key=<key>"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/change-pass.php"
    }
  ]
}
---

# Reset password page

Where a person who followed an emailed reset link chooses a new password.
