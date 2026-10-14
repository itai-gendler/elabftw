---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User unbinds the experiment from their booking",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "event",
          "effect": "reads",
          "facts": [
            "Bound experiment"
          ]
        },
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::scheduler"
        }
      }
    },
    {
      "text": "The Product removes the binding",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "event",
          "effect": "changes",
          "facts": [
            "Bound experiment"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::scheduler"
        }
      }
    }
  ]
}
---

# Unbind a booking

## Trigger

The binding was wrong.

## Outcome

The booking no longer shows the experiment.
