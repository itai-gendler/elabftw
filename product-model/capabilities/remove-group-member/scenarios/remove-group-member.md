---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User, an Admin, removes a person from a group",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "user-group",
          "effect": "reads",
          "facts": [
            "Name",
            "Members"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::admin-panel"
        }
      }
    },
    {
      "text": "The Product removes the person from the group",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user-group",
          "effect": "changes",
          "facts": [
            "Members"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::admin-panel"
        }
      }
    }
  ]
}
---

# Remove a group member

## Trigger

A collaborator left the project.

## Outcome

The person no longer gets what the group is granted.
