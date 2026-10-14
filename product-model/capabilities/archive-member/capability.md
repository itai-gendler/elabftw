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
      "target": "src/Services/UserArchiver.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Users2Teams.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/coordinator-guide.md"
    }
  ]
}
---

# Archive a member

Stop a person from using a team while keeping their work visible, as an Admin where the instance allows it.
