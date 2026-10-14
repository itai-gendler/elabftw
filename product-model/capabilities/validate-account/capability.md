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
      "target": "src/Models/Users/Users.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/admin.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/admin-guide.md"
    }
  ]
}
---

# Validate an account

Let a newly registered person sign in, as an Admin of a team they joined.
