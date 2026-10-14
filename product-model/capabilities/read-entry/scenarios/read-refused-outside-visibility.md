---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User opens a link to an experiment",
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
      "text": "The experiment's visibility does not admit the User, so the Product refuses to show it",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": [
            "Visibility"
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

# Refuse to show an experiment outside its visibility

## Trigger

The User follows a link to an experiment they are not allowed to read.

## Outcome

Nothing of the experiment is shown; the request is refused as forbidden.
