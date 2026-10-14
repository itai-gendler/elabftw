---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User enters their current password and a new one",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::settings"
        }
      }
    },
    {
      "text": "The current password is wrong, so the Product refuses",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Password"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::settings"
        }
      }
    }
  ]
}
---

# Refuse a change with a wrong current password

## Trigger

Someone at the User's desk tries to change the password.

## Outcome

The password is unchanged.
