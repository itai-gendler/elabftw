---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User unticks a finished step",
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
      "text": "The Product marks the step unfinished again",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "step",
          "effect": "changes",
          "from": "Finished",
          "to": "Unfinished",
          "facts": [
            "Finished at"
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

# Unfinish a step

## Trigger

The User ticked a step too early.

## Outcome

The step is to do again; the deadline it lost when finished is not restored.
