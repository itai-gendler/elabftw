---
{
  "entities": [
    {
      "entity": "resource",
      "shows": [
        "Title",
        "Date",
        "Custom ID",
        "Category",
        "Status",
        "Tags",
        "Locked",
        "Timestamped",
        "Owner",
        "Bookable",
        "Main text",
        "eLabID"
      ]
    },
    {
      "entity": "resource-template",
      "shows": [
        "Title"
      ]
    },
    {
      "entity": "status",
      "shows": [
        "Title",
        "Color"
      ]
    }
  ],
  "entryPoints": [
    {
      "web": "/database.php"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/database.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controllers/DatabaseController.php"
    }
  ]
}
---

# Resources

The team's resources the person can read, with the same ordering and filters as Experiments.
