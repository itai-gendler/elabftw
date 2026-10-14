---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses to delete the template",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment-template"
        }
      }
    },
    {
      "text": "The Product moves the template to Deleted",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment-template",
          "effect": "changes",
          "from": "Normal",
          "to": "Deleted",
          "facts": [
            "Title"
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

# Delete an experiment template

## Trigger

A procedure is retired.

## Outcome

The template is no longer offered when creating entries.
