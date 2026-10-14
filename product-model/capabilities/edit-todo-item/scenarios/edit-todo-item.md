---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User changes an item's text",
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
      "text": "The Product saves the item",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "to-do-item",
          "effect": "changes",
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
    }
  ]
}
---

# Edit a to-do item

## Trigger

The reminder needs detail.

## Outcome

The item shows the new text.
