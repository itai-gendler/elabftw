---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User sets a pending request to Validated",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "procurement-request",
          "effect": "reads",
          "facts": [
            "Quantity ordered",
            "Comment"
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
      "text": "The Product records the request as validated",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "procurement-request",
          "effect": "changes",
          "from": "Pending",
          "to": "Validated",
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

# Validate a procurement request

## Trigger

The lab manager approves an order.

## Outcome

The request shows as Validated.
