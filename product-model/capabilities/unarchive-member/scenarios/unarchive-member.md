---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User, an Admin, unarchives a member",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "team-membership",
          "effect": "reads",
          "facts": [
            "Role"
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
      "text": "The Product makes the membership active again",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "team-membership",
          "effect": "changes",
          "from": "Archived",
          "to": "Active",
          "facts": []
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

# Unarchive a member

## Trigger

A former member returns.

## Outcome

The person can sign in to the team again.
