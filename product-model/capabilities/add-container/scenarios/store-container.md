---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Add container, sets the quantity and unit and picks a location",
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
      "text": "The location has room left",
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
    },
    {
      "text": "The Product stores the container at the location for the resource",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "container",
          "effect": "creates",
          "facts": [
            "Quantity",
            "Unit"
          ]
        },
        {
          "entity": "resource",
          "effect": "changes",
          "facts": [
            "Last changed by"
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

# Store a container

## Trigger

A new bottle of buffer goes into the cold room.

## Outcome

The resource lists the container with its location; the changelog records it.

## Edge cases

- A multiplier stores several identical containers at once.
