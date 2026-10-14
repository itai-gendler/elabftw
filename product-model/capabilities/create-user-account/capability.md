---
{
  "availability": [
    {
      "place": "web::signed-in"
    }
  ],
  "domain": "admin-panel",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/UserCreator.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/admin-guide.md"
    }
  ]
}
---

# Create a user account

Create an account for a person in the Admin's team, while the instance lets Admins do so; the person sets a password through password reset.
