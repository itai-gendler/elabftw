---
{
  "entities": [
    {
      "entity": "resource-template",
      "shows": [
        "Title",
        "Main text",
        "Category",
        "Status",
        "Tags",
        "Custom fields",
        "Visibility",
        "Can write",
        "Entry visibility",
        "Entry write permission",
        "Lock down read permissions",
        "Lock down write permissions",
        "Owner",
        "Booking permission"
      ],
      "collects": [
        "Entry visibility",
        "Entry write permission",
        "Lock down read permissions",
        "Lock down write permissions"
      ]
    }
  ],
  "entryPoints": [
    {
      "web": "/resources-templates.php?mode=edit&id=<id>"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/resources-templates.php"
    }
  ]
}
---

# Resource template

One resource template: its content and both sets of permissions.
