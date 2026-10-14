---
{
  "kind": "primary",
  "routes": {
    "api": "API"
  },
  "steps": [
    {
      "text": "The User sends the text of a new action to take",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "api": {
          "place": "api"
        }
      }
    },
    {
      "text": "The Product adds it as an unfinished step of the experiment",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "step",
          "effect": "creates",
          "to": "Unfinished",
          "facts": [
            "Text",
            "Locked"
          ]
        },
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
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

# Add a step through the API

## Trigger

A script plans an experiment's actions.

## Outcome

The API answers 201 Created with the step's address.
