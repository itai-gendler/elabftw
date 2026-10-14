---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User ticks a step",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "step",
          "effect": "reads",
          "facts": [
            "Text"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    },
    {
      "text": "The Product marks the step finished, records when, and clears its deadline and reminder",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "step",
          "effect": "changes",
          "from": "Unfinished",
          "to": "Finished",
          "facts": [
            "Finished at",
            "Deadline"
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

# Finish a step

## Trigger

The User has done one of the planned actions.

## Outcome

The step shows as finished and the next unfinished one becomes the experiment's next step.
