---
{
  "kind": "primary",
  "routes": {
    "api": "API"
  },
  "steps": [
    {
      "text": "The User sends the restore action for a deleted experiment",
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
      "text": "The Product returns the experiment and its attached files to Normal",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "changes",
          "from": "Deleted",
          "to": "Normal",
          "facts": [
            "Last changed by"
          ]
        },
        {
          "entity": "file",
          "effect": "changes",
          "from": "Deleted",
          "to": "Normal",
          "facts": []
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

# Restore an experiment through the API

## Trigger

A script undoes a deletion.

## Outcome

The API returns the restored experiment.
