---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Place order and enters a quantity and a comment",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "comment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::resource"
        }
      }
    },
    {
      "text": "The Product records a pending procurement request for the resource",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
          "effect": "reads",
          "facts": [
            "Procurable",
            "Price"
          ]
        },
        {
          "entity": "procurement-request",
          "effect": "creates",
          "to": "Pending",
          "facts": [
            "Quantity ordered",
            "Comment",
            "Quote"
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

# Place an order

## Trigger

The reagent is running low.

## Outcome

The resource page confirms the order is recorded and the team sees it on its Team page.
