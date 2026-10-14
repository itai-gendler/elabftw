---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User deletes a status",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "status",
          "effect": "reads",
          "facts": [
            "Title"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments-status"
        }
      }
    },
    {
      "text": "The Product stops offering the status",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "status",
          "effect": "changes",
          "from": "Normal",
          "to": "Deleted",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments-status"
        }
      }
    }
  ]
}
---

# Delete a status

## Trigger

A status is no longer used.

## Outcome

The status is no longer offered; entries that show it keep it.
