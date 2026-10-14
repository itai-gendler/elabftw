---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User, an Admin, archives a member",
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
      "text": "The instance lets Admins archive users",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Allow Admins to archive users"
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
      "text": "The Product archives the membership, signs the person out and revokes their API keys bound to it",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "team-membership",
          "effect": "changes",
          "from": "Active",
          "to": "Archived",
          "facts": []
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

# Archive a member

## Trigger

A member left the lab.

## Outcome

The person can no longer sign in to the team; their entries stay readable to others.
