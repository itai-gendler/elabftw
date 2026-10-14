---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User records the packs that arrived",
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
      "text": "The Product records the request as received",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "procurement-request",
          "effect": "changes",
          "from": "Validated",
          "to": "Received",
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

# Receive an order

## Trigger

The delivery came in full.

## Outcome

The request shows as Received.

## Edge cases

- A partial delivery sets the request to Partially received.
