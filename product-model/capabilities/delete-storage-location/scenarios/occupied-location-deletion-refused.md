---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User deletes a location",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "storage-unit",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::inventory"
        }
      }
    },
    {
      "text": "The location still holds other locations or containers, so the Product refuses",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "container",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::inventory"
        }
      }
    }
  ]
}
---

# Refuse to delete a location in use

## Trigger

Someone tries to delete a location in use.

## Outcome

The location stays.
