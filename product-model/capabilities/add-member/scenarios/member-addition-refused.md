---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User, an Admin, picks a person who already has an account",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Name",
            "Email"
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
      "text": "The instance does not let Admins add existing people, so the Product refuses",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Allow Admins to add existing users to their team"
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

# Refuse to add a member

## Trigger

An Admin tries to add a person on an instance that keeps this for Sysadmins.

## Outcome

The person is not added.
