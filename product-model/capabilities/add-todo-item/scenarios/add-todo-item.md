---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User writes an item in the to-do list",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::to-do-list"
        }
      }
    },
    {
      "text": "The Product adds the item at the top of the User's to-do list",
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
        "web": {
          "place": "web::signed-in::to-do-list"
        }
      }
    }
  ]
}
---

# Add a to-do item

## Trigger

The User needs to remember to order gloves.

## Outcome

The item shows in the User's to-do list.
