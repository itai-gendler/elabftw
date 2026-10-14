---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "Someone asked the User to lock the experiment",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "action-request",
          "effect": "reads",
          "facts": [
            "Action",
            "Requester"
          ]
        },
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    },
    {
      "text": "The User chooses Lock",
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
      "text": "The Product locks the experiment and marks the User's lock request done",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Locked",
            "Locked by"
          ]
        },
        {
          "entity": "action-request",
          "effect": "changes",
          "from": "Pending",
          "to": "Done",
          "facts": []
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

# Lock an experiment on request

## Trigger

The User acts on a request to lock an experiment.

## Outcome

The experiment is locked and the request no longer shows as pending.
