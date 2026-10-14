---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User asks the same person for the same action again",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    },
    {
      "text": "A pending request for that action and person already exists, so the Product refuses",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "action-request",
          "effect": "reads",
          "facts": [
            "Action",
            "Target user"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    }
  ]
}
---

# Refuse a repeated request

## Trigger

The User repeats a request still pending.

## Outcome

No new request is recorded.
