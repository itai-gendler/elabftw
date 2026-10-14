---
{
  "kind": "validation",
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
      "text": "The resource does not allow cancelling, or the slot starts too soon, so the Product refuses",
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
    }
  ]
}
---

# Refuse a late cancellation

## Trigger

The User tries to cancel at the last minute.

## Outcome

The booking stays.
