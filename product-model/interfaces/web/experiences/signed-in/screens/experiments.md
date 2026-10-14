---
{
  "entities": [
    {
      "entity": "experiment",
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
        "Main text",
        "eLabID"
      ]
    },
    {
      "entity": "experiment-template",
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
    },
    {
      "entity": "category",
      "shows": [
        "Title"
      ]
    }
  ],
  "entryPoints": [
    {
      "web": "/experiments.php"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/experiments.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controllers/ExperimentsController.php"
    }
  ]
}
---

# Experiments

The team's experiments the person can read, newest change first, with pinned entries on top and filters by category, status, tag, owner and state.
