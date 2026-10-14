---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User adds a location",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::inventory"
        }
      }
    },
    {
      "text": "The instance restricts inventory locations and the User was not given the right, so the Product refuses",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Restrict inventory locations editing"
          ]
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

# Refuse a location when the inventory is restricted

## Trigger

A member tries to change a restricted inventory.

## Outcome

Nothing is added.
