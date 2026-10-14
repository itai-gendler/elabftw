---
{
  "kind": "primary",
  "routes": {
    "api": "API"
  },
  "steps": [
    {
      "text": "The User sends new main text for an experiment",
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
      "text": "The Product saves the main text, keeps it as a new revision and records who changed it",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Main text",
            "Last changed by"
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

# Edit the main text through the API

## Trigger

A script updates an experiment's body.

## Outcome

The API returns the updated experiment.
