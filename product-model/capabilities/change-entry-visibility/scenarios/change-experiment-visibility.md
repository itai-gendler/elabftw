---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User picks a base visibility and any additions",
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
      "text": "The Product saves the experiment's visibility and records who changed it",
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
            "Visibility",
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

# Change an experiment's visibility

## Trigger

The User shares an experiment with their team or keeps it to themselves.

## Outcome

People the new visibility admits can read the experiment and others no longer can, except its owner.

## Edge cases

- A level the instance does not allow is refused.
- Additions widen the base level; they never narrow it.
