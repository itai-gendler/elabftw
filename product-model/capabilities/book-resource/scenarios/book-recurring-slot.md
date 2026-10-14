---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User drags a slot and sets it to repeat weekly on chosen weekdays until a date",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
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
      "text": "Every occurrence respects the resource's booking rules",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
          "effect": "reads",
          "facts": [
            "Overlapping slots allowed",
            "Maximum future bookings per user"
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
      "text": "The Product creates one booking per occurrence, all sharing the recurrence",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "event",
          "effect": "creates",
          "facts": [
            "Title",
            "Start",
            "End",
            "Recurrence"
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

# Book a recurring slot

## Trigger

A group uses an instrument every Monday morning.

## Outcome

Each occurrence shows in the scheduler as a booking of its own.

## Edge cases

- A recurrence has at most 100 occurrences over at most 10 years.
- A monthly recurrence on a day missing from some months is refused.
