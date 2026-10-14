---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User writes what has to be done next",
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
      "text": "The Product adds it as an unfinished step of the experiment",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "step",
          "effect": "creates",
          "to": "Unfinished",
          "facts": [
            "Text",
            "Locked"
          ]
        },
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
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

# Add a step

## Trigger

The User plans the actions an experiment needs.

## Outcome

The step appears on the experiment, and as its next step in lists and the to-do list.
