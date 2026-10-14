---
{
  "kind": "primary",
  "routes": {
    "api": "API"
  },
  "steps": [
    {
      "text": "The User requests an experiment in ZIP format",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "api": {
          "place": "api"
        }
      }
    },
    {
      "text": "The Product returns a ZIP archive with the experiment's export and files",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": [
            "Title",
            "Date",
            "Main text",
            "Custom ID",
            "Category",
            "Status",
            "Tags",
            "Custom fields",
            "eLabID",
            "Owner"
          ]
        }
      ],
      "contexts": {
        "api": {
          "place": "api"
        }
      }
    }
  ]
}
---

# Export an experiment through the API

## Trigger

A backup script archives experiments.

## Outcome

The API streams the archive.
