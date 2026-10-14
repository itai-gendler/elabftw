---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User searches for an experiment and binds it to their booking",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": [
            "Title"
          ]
        },
        {
          "entity": "event",
          "effect": "reads",
          "facts": [
            "Title"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::scheduler"
        }
      }
    },
    {
      "text": "The Product binds the booking to the experiment",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": []
        },
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

# Bind a booking to an experiment

## Trigger

The User records which experiment used the slot.

## Outcome

The booking shows the experiment to those who can read it.
