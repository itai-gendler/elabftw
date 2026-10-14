---
{
  "availability": [
    {
      "place": "web::public"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/app/controllers/RegisterController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Users/Users.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/TeamsHelper.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/install/post-install/1-register.md"
    }
  ]
}
---

# Create an account

Register one's own account and ask to join a team, while the instance allows local registration. The first account of an instance becomes its Sysadmin and the first member of a team its Admin.
