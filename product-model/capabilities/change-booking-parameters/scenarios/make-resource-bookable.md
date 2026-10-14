---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User allows booking the resource and sets its limits",
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
      "text": "The Product saves the booking parameters on the resource",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
          "effect": "changes",
          "facts": [
            "Bookable",
            "Overlapping slots allowed",
            "Maximum time per slot",
            "Maximum future bookings per user",
            "Booking window",
            "Booking in the past allowed",
            "Cancellable",
            "Minimum cancellation notice",
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

# Make a resource bookable

## Trigger

The lab wants its confocal microscope booked through the scheduler.

## Outcome

The resource can be booked in the scheduler within these limits.
