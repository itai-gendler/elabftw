---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User, an Admin, deletes a group",
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
      "text": "The Product removes the group",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user-group",
          "effect": "removes"
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

# Delete a user group

## Trigger

The project ended.

## Outcome

The group is gone.
