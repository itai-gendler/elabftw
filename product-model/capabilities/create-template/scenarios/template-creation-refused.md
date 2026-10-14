---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Create",
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
      "text": "The team keeps creating templates for its Admins and the User is not one, so the Product refuses",
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
    }
  ]
}
---

# Refuse template creation

## Trigger

A member tries to create a template in a team that restricts them.

## Outcome

No template is created.
