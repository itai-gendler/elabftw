---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User, the experiment's owner but not an Admin, chooses Transfer ownership",
      "kind": "actor",
      "actor": "user",
      "entities": [
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
      "text": "The Product refuses: only an administrator of the entry's team can transfer ownership",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": [
            "Owner"
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

# Refuse an ownership transfer by the owner

## Trigger

An owner who is not an Admin tries to hand over their experiment.

## Outcome

The experiment keeps its owner.
