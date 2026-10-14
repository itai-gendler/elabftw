---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User drags their booking to another time",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "event",
          "effect": "reads",
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
    },
    {
      "text": "The new time respects the resource's booking rules",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
          "effect": "reads",
          "facts": [
            "Overlapping slots allowed",
            "Maximum time per slot",
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
      "text": "The Product moves the booking",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "event",
          "effect": "changes",
          "facts": [
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

# Move a booking

## Trigger

The User's plans changed.

## Outcome

The booking shows at its new time.

## Decision points

### Which occurrences change?

Is the booking one occurrence of a recurrence, edited through Edit?

- The User picks only this one → only this occurrence changes
- The User picks this one and the following → this and every later occurrence change
- The User picks the whole recurrence → every occurrence changes

## Edge cases

- Dragging an occurrence in the calendar changes only that occurrence.
