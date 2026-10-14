---
{
  "kind": "primary",
  "routes": {
    "api": "API"
  },
  "steps": [
    {
      "text": "The User requests a resource by its id",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
          "effect": "reads",
          "facts": [
            "Title",
            "Date",
            "Main text",
            "Status",
            "Category",
            "Tags",
            "Custom fields",
            "Visibility",
            "Can write",
            "Locked",
            "eLabID",
            "Owner",
            "Bookable"
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

# Read a resource through the API

## Trigger

A script reads one resource.

## Outcome

The API returns the resource with its steps, links, attached files, comments and changelog.
