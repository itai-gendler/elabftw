---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User picks who may book the resource",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
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
      "text": "The Product saves the resource's booking permission",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
          "effect": "changes",
          "facts": [
            "Booking permission",
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

# Change who can book a resource

## Trigger

Only the imaging group should book the microscope.

## Outcome

Only the people the new setting admits can book the resource.
