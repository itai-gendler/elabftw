---
{
  "entities": [
    {
      "entity": "account",
      "collects": [
        "Name",
        "Email",
        "Password"
      ]
    },
    {
      "entity": "team",
      "shows": [
        "Name"
      ]
    }
  ],
  "entryPoints": [
    {
      "web": "/register.php"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/register.php"
    }
  ]
}
---

# Registration page

Where a person creates their own account and picks the team they want to join.
