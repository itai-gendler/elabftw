---
{
  "kind": "validation",
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
          "place": "web::signed-in::experiments-categories"
        }
      }
    },
    {
      "text": "The team keeps this list for its Admins and the User is not one, so the Product refuses",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": [
            "Allow users to create and edit experiments categories"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments-categories"
        }
      }
    }
  ]
}
---

# Refuse to create a category

## Trigger

A member tries to add a category in a team that restricts them.

## Outcome

No category is added.
