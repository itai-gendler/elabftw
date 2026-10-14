---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User archives a received request",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "procurement-request",
          "effect": "reads",
          "facts": [
            "Quantity received"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::team"
        }
      }
    },
    {
      "text": "The Product archives the request",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "procurement-request",
          "effect": "changes",
          "from": "Received",
          "to": "Archived",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::team"
        }
      }
    }
  ]
}
---

# Archive a procurement request

## Trigger

The order is complete.

## Outcome

The request is kept as Archived.
