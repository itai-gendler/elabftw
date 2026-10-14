---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User adds a location named “Freezer 4” inside a room",
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
      "text": "The Product adds the location to the inventory tree",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "storage-unit",
          "effect": "creates",
          "facts": [
            "Name",
            "Parent",
            "Capacity"
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

# Add a storage location

## Trigger

The lab maps where things are kept.

## Outcome

The location appears in the tree, ready to hold containers.
