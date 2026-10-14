---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Archive",
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
      "text": "The Product archives the resource and locks it, recording the User as its locker",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
          "effect": "changes",
          "from": "Normal",
          "to": "Archived",
          "facts": [
            "Locked",
            "Locked by",
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

# Archive a resource

## Trigger

A piece of equipment is retired.

## Outcome

The resource is Archived and locked and no longer listed by default.
