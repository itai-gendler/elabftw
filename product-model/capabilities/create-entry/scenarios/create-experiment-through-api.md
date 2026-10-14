---
{
  "kind": "primary",
  "routes": {
    "api": "API"
  },
  "steps": [
    {
      "text": "The User sends a create request with a title and, optionally, tags, a category and permissions",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "category",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "tag",
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
      "text": "The Product creates a Normal experiment owned by the User in the team the key acts in",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Default visibility",
            "Default write permission",
            "Markdown editor"
          ]
        },
        {
          "entity": "team",
          "effect": "reads",
          "facts": [
            "Allow users to create experiments",
            "Force experiment template use"
          ]
        },
        {
          "entity": "experiment",
          "effect": "creates",
          "to": "Normal",
          "facts": [
            "Title",
            "Date",
            "Main text",
            "Custom ID",
            "Category",
            "Status",
            "Tags",
            "Custom fields",
            "Visibility",
            "Can write",
            "Visibility locked down",
            "Can write locked down",
            "Locked",
            "Timestamped",
            "Signature count",
            "eLabID",
            "Owner",
            "Team"
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

# Create an experiment through the API

## Trigger

A script creates an experiment for its holder.

## Outcome

The API answers 201 Created with the new experiment's address.
