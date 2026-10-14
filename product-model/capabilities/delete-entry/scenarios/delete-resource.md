---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Delete entry",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::resource"
        }
      }
    },
    {
      "text": "The Product moves the resource and its attached files to Deleted and releases its Custom ID",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
          "effect": "changes",
          "from": "Normal",
          "to": "Deleted",
          "facts": [
            "Custom ID",
            "Last changed by"
          ]
        },
        {
          "entity": "file",
          "effect": "changes",
          "from": "Normal",
          "to": "Deleted",
          "facts": []
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

# Delete a resource

## Trigger

A resource was recorded twice.

## Outcome

The resource is Deleted and restorable.
