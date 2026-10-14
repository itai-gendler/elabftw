---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User, an Admin, picks a person to add to a group",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "user-group",
          "effect": "reads",
          "facts": [
            "Name"
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
      "text": "The Product adds the person to the group",
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

# Add a group member

## Trigger

A collaborator joins the project.

## Outcome

The person reads and writes what the group is granted.
