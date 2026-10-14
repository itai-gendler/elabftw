---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User drags their booking into the past",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "event",
          "effect": "reads",
          "facts": [
            "Start"
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
      "text": "The User is not an Admin and the resource does not allow booking in the past, so the Product refuses",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
          "effect": "reads",
          "facts": [
            "Booking in the past allowed"
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

# Refuse to move a booking into the past

## Trigger

Someone tries to rewrite a past booking.

## Outcome

The booking keeps its time.
