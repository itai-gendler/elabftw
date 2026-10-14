---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Create on the resources list and starts from a template",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "resource-template",
          "effect": "reads",
          "facts": [
            "Title"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::resources"
        }
      }
    },
    {
      "text": "The team lets the User create resources",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": [
            "Allow users to create resources"
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
          "place": "web::signed-in::resources"
        }
      }
    },
    {
      "text": "The Product creates a Normal resource from the template, copying its content, steps, attached files and the permissions it sets for new entries",
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
            "Lock down write permissions",
            "Booking permission"
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
            "Bookable",
            "Booking permission"
          ]
        },
        {
          "entity": "step",
          "effect": "creates",
          "to": "Unfinished",
          "facts": [
            "Text",
            "Deadline",
            "Locked"
          ],
          "with": "resource"
        },
        {
          "entity": "file",
          "effect": "creates",
          "to": "Normal",
          "facts": [
            "Name",
            "Comment",
            "Immutable"
          ],
          "with": "resource"
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::resources"
        }
      }
    }
  ]
}
---

# Create a resource from a template

## Trigger

The User adds a new antibody, plasmid or instrument to the team's database.

## Outcome

A new Normal resource carries the template's content and starts with its entry and booking permissions; it is not bookable until someone makes it so.
