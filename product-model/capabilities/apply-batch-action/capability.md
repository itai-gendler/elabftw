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
      "target": "src/Models/Batch.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/admin-guide.md"
    }
  ]
}
---

# Apply a batch action

Apply one action, such as lock, archive, change visibility or transfer ownership, to every entry of chosen categories, statuses, tags or owners, from the Batch actions tab of the Admin panel.
