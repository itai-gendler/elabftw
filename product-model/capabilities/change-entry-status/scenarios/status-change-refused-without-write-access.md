---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User picks a status on an experiment they can only read",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "status",
          "effect": "reads",
          "facts": []
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
      "text": "The experiment's write permission does not admit the User, so the Product refuses",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": [
            "Can write"
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

# Refuse a status change without write access

## Trigger

A reader tries to change the status.

## Outcome

The status is unchanged.
