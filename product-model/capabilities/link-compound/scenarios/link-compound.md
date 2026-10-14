---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User picks a compound in the compounds section",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "compound",
          "effect": "reads",
          "facts": [
            "Name"
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
      "text": "The Product links the compound to the experiment",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "compound",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Compounds",
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

# Link a compound

## Trigger

The User records the compounds an experiment used.

## Outcome

The experiment lists the compound with its hazards.
