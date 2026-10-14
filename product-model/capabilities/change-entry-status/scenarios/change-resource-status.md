---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User picks a status",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "status",
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
      "text": "The Product sets it as the resource's status and records who changed it",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "status",
          "effect": "reads",
          "facts": [
            "Title"
          ]
        },
        {
          "entity": "resource",
          "effect": "changes",
          "facts": [
            "Status",
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

# Change a resource's status

## Trigger

A resource runs low, is in use or is out of order.

## Outcome

The resource shows the new status.
