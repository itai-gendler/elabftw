---
{
  "kind": "primary",
  "routes": {
    "api": "API"
  },
  "steps": [
    {
      "text": "The User sends the timestamp action for an experiment",
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
      "text": "The Product exports and certifies the experiment and attaches the archive",
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
        },
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Timestamping authority",
            "Monthly timestamp limit"
          ]
        },
        {
          "entity": "file",
          "effect": "creates",
          "to": "Archived",
          "facts": [
            "Name",
            "Comment",
            "Immutable"
          ]
        }
      ],
      "contexts": {
        "api": {
          "place": "api"
        }
      }
    },
    {
      "text": "The Product marks the experiment timestamped, counts down the timestamp balance and keeps a revision",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Timestamped",
            "Timestamped at"
          ]
        },
        {
          "entity": "instance-settings",
          "effect": "changes",
          "facts": [
            "Timestamp balance"
          ]
        },
        {
          "entity": "revision",
          "effect": "creates",
          "facts": [
            "Main text",
            "Saved at"
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

# Timestamp an experiment through the API

## Trigger

A script timestamps experiments on a schedule.

## Outcome

The API returns the timestamped experiment.
