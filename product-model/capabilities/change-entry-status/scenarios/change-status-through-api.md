---
{
  "kind": "primary",
  "routes": {
    "api": "API"
  },
  "steps": [
    {
      "text": "The User sends a status for an experiment",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "status",
          "effect": "reads",
          "facts": []
        },
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
      "text": "The Product sets the experiment's status and records who changed it",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "status",
          "effect": "reads",
          "facts": [
            "Title"
          ]
        },
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Status",
            "Last changed by"
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

# Change a status through the API

## Trigger

A script records an outcome.

## Outcome

The API returns the updated experiment.
