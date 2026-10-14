---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User changes a status's name or color",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "status",
          "effect": "reads",
          "facts": [
            "Title",
            "Color"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments-status"
        }
      }
    },
    {
      "text": "The Product saves the status",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "status",
          "effect": "changes",
          "facts": [
            "Title",
            "Color"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments-status"
        }
      }
    }
  ]
}
---

# Edit a status

## Trigger

A status name no longer fits.

## Outcome

Every entry showing the status shows the new name and color.
