---
{
  "availability": [
    {
      "place": "web::signed-in"
    },
    {
      "place": "api"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractEntity.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/ExclusiveEditMode.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Revisions.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/templates/view.html"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/user-guide/experiments.md"
    }
  ]
}
---

# Edit an entry

Change an entry's own content: title, date, main text and custom field values. Fields save as they change; the main text saves on demand and by autosave. While someone has an entry open in edit mode, others cannot change it.
