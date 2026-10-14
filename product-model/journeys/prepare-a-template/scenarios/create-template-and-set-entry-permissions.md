---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Create and enters a title",
      "kind": "actor",
      "capability": "create-template",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment-templates"
        }
      }
    },
    {
      "text": "The Product creates the template and opens it in edit mode",
      "kind": "product",
      "capability": "create-template",
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
    },
    {
      "text": "The User sets the permissions new entries get",
      "kind": "actor",
      "capability": "change-template-entry-permissions",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment-template"
        }
      }
    },
    {
      "text": "The Product saves them on the template",
      "kind": "product",
      "capability": "change-template-entry-permissions",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment-template",
          "effect": "changes",
          "facts": [
            "Entry visibility",
            "Entry write permission",
            "Lock down read permissions",
            "Lock down write permissions"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment-template"
        }
      }
    }
  ]
}
---

# Create a template and set its entry permissions

## Trigger

The User standardizes a procedure for the team.

## Outcome

The template is ready for the team to use.
