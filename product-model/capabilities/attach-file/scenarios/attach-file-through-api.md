---
{
  "kind": "primary",
  "routes": {
    "api": "API"
  },
  "steps": [
    {
      "text": "The User uploads a file for an experiment",
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
      "text": "The Product attaches the file to the experiment",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "file",
          "effect": "creates",
          "to": "Normal",
          "facts": [
            "Name",
            "Comment",
            "Immutable"
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

# Attach a file through the API

## Trigger

An instrument script uploads its output.

## Outcome

The API answers 201 Created with the file's address.
