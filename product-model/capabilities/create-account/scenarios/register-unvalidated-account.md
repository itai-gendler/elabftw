---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Visitor enters a name, email and password and picks a team",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::public::register"
        }
      }
    },
    {
      "text": "Admin validation is on",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Admin validation"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::public::register"
        }
      }
    },
    {
      "text": "The Product creates an unvalidated account in the chosen team and notifies the team's Admins",
      "kind": "product",
      "actor": "visitor",
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
            "Password",
            "Validated",
            "Preferred language",
            "Default visibility",
            "Default write permission"
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
          "place": "web::public::register"
        }
      }
    }
  ]
}
---

# Register and await validation

## Trigger

A new lab member signs up on an instance that vets accounts.

## Outcome

The person is told the account must be validated by an Admin and that an email will follow; they cannot sign in yet.
