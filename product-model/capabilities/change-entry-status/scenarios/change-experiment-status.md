---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User picks a status",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "status",
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
      "text": "The Product sets it as the experiment's status and records who changed it",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "status",
          "effect": "reads",
          "facts": [
            "Title"
          ]
        },
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Status",
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

# Change an experiment's status

## Trigger

The User's experiment succeeded, failed or needs to be redone.

## Outcome

The experiment shows the new status, in lists too, and its changelog records the change.
