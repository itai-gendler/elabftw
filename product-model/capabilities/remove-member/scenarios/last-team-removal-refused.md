---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User, an Admin, removes a member",
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
      "text": "It is the person's only team, so the Product refuses",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
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

# Refuse to remove a person's last team

## Trigger

An Admin tries to remove someone from their only team.

## Outcome

The membership stays.
