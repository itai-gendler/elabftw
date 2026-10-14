---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User, an Admin, enters a name and email for a new member",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::admin-panel"
        }
      }
    },
    {
      "text": "The instance lets Admins create accounts",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Admins can create local accounts"
          ]
        },
        {
          "entity": "account",
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
      "text": "The Product creates a validated account in the team",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        },
        {
          "entity": "account",
          "effect": "creates",
          "facts": [
            "Name",
            "Email",
            "Validated"
          ]
        },
        {
          "entity": "team-membership",
          "effect": "creates",
          "to": "Active",
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

# Create a user account

## Trigger

A new student starts in the lab.

## Outcome

The account exists in the team; its holder resets the password to sign in.
