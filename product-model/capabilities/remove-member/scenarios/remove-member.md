---
{
  "kind": "primary",
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
      "text": "The person belongs to another team as well",
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
    },
    {
      "text": "The Product ends the membership and revokes the person's API keys bound to it",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "team-membership",
          "effect": "removes",
          "from": "Active"
        },
        {
          "entity": "api-key",
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

# Remove a member

## Trigger

A member moved to another team for good.

## Outcome

The person no longer belongs to the team.
