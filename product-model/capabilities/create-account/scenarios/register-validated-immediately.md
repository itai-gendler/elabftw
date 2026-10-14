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
      "text": "Registration is open, the password meets the requirement and Admin validation is off",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Local registration",
            "Minimum password length",
            "Password requirement",
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
      "text": "The Product creates a validated account and makes the person a member of the chosen team",
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

# Register with immediate validation

## Trigger

A new lab member signs up on an instance that trusts registrations.

## Outcome

The account exists and can sign in at once; the team's Admins are told someone joined.

## Decision points

### Which role does the person get?

Is the account the first of the instance or of the team?

- First account of the instance → the person becomes a Sysadmin and the team's Admin, validated
- First member of the team → the person becomes its Admin, validated
- Otherwise → the person becomes a User of the team
