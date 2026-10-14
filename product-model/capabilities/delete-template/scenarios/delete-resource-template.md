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
          "place": "web::signed-in::resource-template"
        }
      }
    },
    {
      "text": "The Product moves the template to Deleted",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "resource-template",
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
          "place": "web::signed-in::resource-template"
        }
      }
    }
  ]
}
---

# Delete a resource template

## Trigger

A kind of material is no longer recorded.

## Outcome

The template is no longer offered when creating resources.
