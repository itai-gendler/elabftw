---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User enters a name and colors",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::resources-categories"
        }
      }
    },
    {
      "text": "The team lets members manage this list, or the User is an Admin",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": [
            "Allow users to create and edit resources categories"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::resources-categories"
        }
      }
    },
    {
      "text": "The Product adds the new private category to the team's list",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "category",
          "effect": "creates",
          "to": "Normal",
          "facts": [
            "Title",
            "Color",
            "Text color",
            "Private",
            "Applies to"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::resources-categories"
        }
      }
    }
  ]
}
---

# Create a resource category

## Trigger

The lab starts keeping plasmids.

## Outcome

The category is offered on the team's resources and Resource templates.
