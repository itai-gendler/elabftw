---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User picks a category",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "category",
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
      "text": "The Product sets it as the experiment's category and records who changed it",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "category",
          "effect": "reads",
          "facts": [
            "Title"
          ]
        },
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Category",
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

# Change an experiment's category

## Trigger

The User files an experiment under a project.

## Outcome

The experiment shows the category and can be found through it; its Custom ID is unchanged.
