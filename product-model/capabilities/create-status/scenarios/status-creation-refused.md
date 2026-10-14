---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User enters a name and a color",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments-status"
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
            "Allow users to create and edit experiment status"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments-status"
        }
      }
    }
  ]
}
---

# Refuse to create a status

## Trigger

A member tries to add a status in a team that restricts them.

## Outcome

No status is added.
