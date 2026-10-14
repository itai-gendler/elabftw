---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The experiment's visibility is locked down by its template",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": [
            "Visibility locked down"
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
      "text": "The User, an Admin, picks a new visibility",
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

# An Admin changes a locked-down visibility

## Trigger

An Admin needs to widen or restrict an entry whose template locked its visibility.

## Outcome

The experiment has the new visibility.
