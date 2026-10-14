---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User deletes an empty location",
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
      "text": "The Product removes the location",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "storage-unit",
          "effect": "removes"
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

# Delete a storage location

## Trigger

A freezer was decommissioned.

## Outcome

The location is gone from the tree.
