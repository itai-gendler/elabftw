---
{
  "kind": "primary",
  "routes": {
    "api": "API"
  },
  "steps": [
    {
      "text": "The User sends a quantity, a unit and a location for a resource",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "storage-unit",
          "effect": "reads",
          "facts": []
        },
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
        "api": {
          "place": "api"
        }
      }
    }
  ]
}
---

# Add a container through the API

## Trigger

A stock script records deliveries.

## Outcome

The API answers 201 Created.
