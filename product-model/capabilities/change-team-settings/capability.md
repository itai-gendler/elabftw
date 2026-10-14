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
      "target": "src/Models/Teams.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/templates/admin.html"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/admin-guide.md"
    }
  ]
}
---

# Change team settings

Set, as an Admin, what the team's members may create and whether templates are forced, on the Team tab of the Admin panel.
