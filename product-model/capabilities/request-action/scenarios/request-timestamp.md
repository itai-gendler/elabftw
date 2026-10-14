---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Request action, picks Timestamp and a person to ask",
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
      "text": "The Product records the pending request on the experiment and notifies that person",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "action-request",
          "effect": "creates",
          "to": "Pending",
          "facts": [
            "Action",
            "Requester",
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

# Request a timestamp

## Trigger

The User wants a colleague to timestamp their experiment.

## Outcome

The request shows on the experiment and in the target person's notifications until they act on it.
