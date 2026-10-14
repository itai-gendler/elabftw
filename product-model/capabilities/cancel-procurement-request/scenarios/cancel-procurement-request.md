---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User cancels a pending request",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "procurement-request",
          "effect": "reads",
          "facts": [
            "Quantity ordered"
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
      "text": "The Product marks the request cancelled",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "procurement-request",
          "effect": "changes",
          "from": "Pending",
          "to": "Cancelled",
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

# Cancel a procurement request

## Trigger

The order is no longer needed.

## Outcome

The request shows as Cancelled and stays on record.
