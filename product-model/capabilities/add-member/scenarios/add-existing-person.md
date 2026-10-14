---
{
  "kind": "primary",
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
      "text": "The instance lets Admins add existing people",
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
    },
    {
      "text": "The Product adds the person to the team as a User",
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

# Add an existing person

## Trigger

A colleague from another team joins the Admin's lab.

## Outcome

The person can work in the team and, if validated, receives its onboarding email.
