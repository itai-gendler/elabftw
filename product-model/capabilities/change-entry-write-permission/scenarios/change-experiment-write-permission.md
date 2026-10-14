---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User picks a base write permission and any additions",
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
      "text": "The Product saves the experiment's write permission and records who changed it",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Allowed visibility levels"
          ]
        },
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Can write",
            "Last changed by"
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

# Change who can write an experiment

## Trigger

The User lets their team edit an experiment.

## Outcome

People the new setting admits can change the experiment; its owner always can.
