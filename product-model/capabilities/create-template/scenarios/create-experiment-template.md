---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Create and enters a title",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment-templates"
        }
      }
    },
    {
      "text": "The team lets the User create templates",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": [
            "Allow users to create experiments templates"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment-templates"
        }
      }
    },
    {
      "text": "The Product creates the template, owned by the User, with entry permissions equal to its own",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment-template",
          "effect": "creates",
          "facts": [
            "Title",
            "Main text",
            "Visibility",
            "Can write",
            "Entry visibility",
            "Entry write permission",
            "Lock down read permissions",
            "Lock down write permissions",
            "Owner",
            "Team"
          ],
          "to": "Normal"
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment-templates"
        }
      }
    }
  ]
}
---

# Create an experiment template

## Trigger

The User captures a recurring procedure for the team.

## Outcome

The new experiment template opens in edit mode.
