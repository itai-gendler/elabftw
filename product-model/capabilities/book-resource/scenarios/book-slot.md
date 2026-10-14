---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User picks a bookable resource, drags a slot in the calendar and confirms its title",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
          "effect": "reads",
          "facts": [
            "Title",
            "Bookable"
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
      "text": "The slot respects the resource's booking limits and overlaps no booking where overlapping is not allowed",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
          "effect": "reads",
          "facts": [
            "Overlapping slots allowed",
            "Maximum time per slot",
            "Maximum future bookings per user",
            "Booking window"
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
      "text": "The Product creates the booking for the User",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "event",
          "effect": "creates",
          "facts": [
            "Title",
            "Start",
            "End"
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

# Book a slot

## Trigger

The User needs the microscope on Tuesday afternoon.

## Outcome

The booking shows in the scheduler and on the User's dashboard.

## Edge cases

- Several resources can be booked for the same slot at once.
