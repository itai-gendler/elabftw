---
{
  "kind": "primary",
  "routes": {
    "api": "API"
  },
  "steps": [
    {
      "text": "The User sends the text of a to-do item",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "to-do-item",
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
      "text": "The Product adds the item to the User's to-do list",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "to-do-item",
          "effect": "creates",
          "facts": [
            "Text",
            "Order"
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

# Add a to-do item through the API

## Trigger

A script adds reminders.

## Outcome

The API answers 201 Created.
