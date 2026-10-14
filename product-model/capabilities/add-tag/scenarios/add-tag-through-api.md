---
{
  "kind": "primary",
  "routes": {
    "api": "API"
  },
  "steps": [
    {
      "text": "The User sends a tag name for an experiment",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "tag",
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
      "text": "The Product attaches the tag to the experiment, creating it where the team allows",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": [
            "Allow users to create new tags"
          ]
        },
        {
          "entity": "tag",
          "effect": "creates",
          "facts": [
            "Name"
          ]
        },
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Tags"
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

# Add a tag through the API

## Trigger

An import script labels experiments.

## Outcome

The API answers 201 Created.
