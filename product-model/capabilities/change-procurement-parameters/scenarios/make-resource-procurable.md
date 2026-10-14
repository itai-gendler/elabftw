---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User makes the resource procurable and sets its pack quantity and price",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
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
      "text": "The Product saves the procurement parameters on the resource",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
          "effect": "changes",
          "facts": [
            "Procurable",
            "Pack quantity",
            "Price",
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

# Make a resource procurable

## Trigger

The team orders a reagent regularly.

## Outcome

The resource shows Place order.
