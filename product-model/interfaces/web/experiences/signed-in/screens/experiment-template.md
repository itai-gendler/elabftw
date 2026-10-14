---
{
  "entities": [
    {
      "entity": "experiment-template",
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
        "Owner"
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
      "web": "/templates.php?mode=edit&id=<id>"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/templates.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/templates/view-edit-target-permissions.html"
    }
  ]
}
---

# Experiment template

One experiment template: its content and both sets of permissions, its own and those of the experiments created from it.
