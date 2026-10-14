---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User, an Admin, makes a member an Admin",
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
      "text": "The Product sets the membership's role to Admin, sending the admin onboarding email the first time the person becomes an Admin",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "team-membership",
          "effect": "changes",
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
    }
  ]
}
---

# Promote a member to Admin

## Trigger

The lab needs a second Admin.

## Outcome

The member can open the Admin panel of the team.
