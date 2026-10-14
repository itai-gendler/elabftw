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
          "place": "web::signed-in::resource-templates"
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
            "Allow users to create resources templates"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::resource-templates"
        }
      }
    },
    {
      "text": "The Product creates the template, owned by the User, with entry permissions equal to its own",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "resource-template",
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
            "Team",
            "Booking permission"
          ],
          "to": "Normal"
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::resource-templates"
        }
      }
    }
  ]
}
---

# Create a resource template

## Trigger

The User defines how the team records a kind of material.

## Outcome

The new resource template opens in edit mode.
