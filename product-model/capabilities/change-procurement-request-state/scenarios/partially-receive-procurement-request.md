---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User records that part of the order arrived",
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
      "text": "The Product records the request as partially received",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "procurement-request",
          "effect": "changes",
          "from": "Validated",
          "to": "Partially received",
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
    }
  ]
}
---

# Partially receive an order

## Trigger

Half the delivery came.

## Outcome

The request shows as Partially received.
