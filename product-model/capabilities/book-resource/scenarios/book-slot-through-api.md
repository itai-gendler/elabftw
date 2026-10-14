---
{
  "kind": "primary",
  "routes": {
    "api": "API"
  },
  "steps": [
    {
      "text": "The User sends a start, an end and a title for a resource",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
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
      "text": "The Product creates the booking for the User",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "event",
          "effect": "creates",
          "facts": [
            "Title",
            "Start",
            "End"
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

# Book a slot through the API

## Trigger

A facility tool books instruments.

## Outcome

The API answers 201 Created with the booking's address.
