---
{
  "kind": "validation",
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
      "text": "The instance keeps archiving for instance administrators, so the Product refuses",
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
    }
  ]
}
---

# Refuse archiving when the instance keeps it for Sysadmins

## Trigger

An Admin tries to archive a member on an instance that keeps this for Sysadmins.

## Outcome

The membership stays active.
