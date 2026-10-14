---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User deletes an item",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "to-do-item",
          "effect": "reads",
          "facts": [
            "Text"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::to-do-list"
        }
      }
    },
    {
      "text": "The Product removes the item",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "to-do-item",
          "effect": "removes"
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::to-do-list"
        }
      }
    }
  ]
}
---

# Delete a to-do item

## Trigger

The task is done.

## Outcome

The item is gone.
