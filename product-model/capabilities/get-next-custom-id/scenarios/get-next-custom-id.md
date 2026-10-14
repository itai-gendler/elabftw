---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Get next",
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
      "text": "The Product gives the experiment the number after the highest Custom ID in its category",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "category",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Custom ID",
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

# Get the next Custom ID

## Trigger

The User wants their experiment numbered within its category.

## Outcome

The experiment shows the new Custom ID before its title.
