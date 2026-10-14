---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User picks a location for a new container",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "storage-unit",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        },
        {
          "entity": "container",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::resource"
        }
      }
    },
    {
      "text": "The location is at capacity, so the Product refuses",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "storage-unit",
          "effect": "reads",
          "facts": [
            "Capacity"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::resource"
        }
      }
    }
  ]
}
---

# Refuse a container at a full location

## Trigger

The freezer shelf is full.

## Outcome

No container is added.
