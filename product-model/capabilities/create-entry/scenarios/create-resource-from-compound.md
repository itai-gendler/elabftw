---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Create resource from compound and picks a template",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "compound",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        },
        {
          "entity": "resource-template",
          "effect": "reads",
          "facts": [
            "Title"
          ]
        },
        {
          "entity": "resource",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::compounds"
        }
      }
    },
    {
      "text": "The Product creates a Normal resource from the template, named after the compound and referring to it",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "resource-template",
          "effect": "reads",
          "facts": [
            "Title",
            "Main text",
            "Category",
            "Status",
            "Tags",
            "Custom fields",
            "Entry visibility",
            "Entry write permission",
            "Lock down read permissions",
            "Lock down write permissions"
          ]
        },
        {
          "entity": "compound",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        },
        {
          "entity": "resource",
          "effect": "creates",
          "to": "Normal",
          "facts": [
            "Title",
            "Date",
            "Main text",
            "Custom ID",
            "Category",
            "Status",
            "Tags",
            "Custom fields",
            "Visibility",
            "Can write",
            "Visibility locked down",
            "Can write locked down",
            "Locked",
            "Timestamped",
            "Signature count",
            "eLabID",
            "Owner",
            "Team",
            "Created from",
            "Compounds"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::compounds"
        }
      }
    }
  ]
}
---

# Create a resource from a compound

## Trigger

The User keeps a bottle of a compound and wants it in the resource database.

## Outcome

A new resource named after the compound opens in edit mode, linked to it.
