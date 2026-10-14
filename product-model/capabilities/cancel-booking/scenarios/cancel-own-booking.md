---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Cancel on their booking",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "event",
          "effect": "reads",
          "facts": [
            "Title",
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
      "text": "The resource lets its bookings be cancelled this close to their start",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
          "effect": "reads",
          "facts": [
            "Cancellable",
            "Minimum cancellation notice"
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
      "text": "The Product removes the booking and notifies the Admins",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "event",
          "effect": "removes"
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

# Cancel one's own booking

## Trigger

The User no longer needs the slot.

## Outcome

The slot is free for others.

## Edge cases

- A booking created in the last few minutes can be cancelled even if it has started.
