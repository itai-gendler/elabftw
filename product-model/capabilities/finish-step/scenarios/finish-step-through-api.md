---
{
  "kind": "primary",
  "routes": {
    "api": "API"
  },
  "steps": [
    {
      "text": "The User sends the finish action for a step",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "step",
          "effect": "reads",
          "facts": [
            "Text"
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
      "text": "The Product marks the step finished and clears its deadline",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "step",
          "effect": "changes",
          "from": "Unfinished",
          "to": "Finished",
          "facts": [
            "Finished at",
            "Deadline"
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

# Finish a step through the API

## Trigger

An instrument reports a stage as done.

## Outcome

The API returns the finished step.
