---
{
  "kind": "primary",
  "result": "not-achieved",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Visitor registers with a name, email and password and picks a team",
      "kind": "actor",
      "capability": "create-account",
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
      "text": "The Product creates an unvalidated account in the team",
      "kind": "product",
      "capability": "create-account",
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
    },
    {
      "text": "The Product returns the Visitor to the sign-in page with the email filled in",
      "kind": "product",
      "capability": "create-account",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::public::login"
        }
      }
    },
    {
      "text": "The Visitor enters their password",
      "kind": "actor",
      "capability": "sign-in",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::public::login"
        }
      }
    },
    {
      "text": "The account is not validated yet, so the Product refuses",
      "kind": "condition",
      "capability": "sign-in",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Validated"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::public::login"
        }
      }
    }
  ]
}
---

# Register and wait for validation

## Trigger

A newcomer joins on an instance that vets accounts.

## Outcome

The newcomer cannot sign in until an Admin validates the account.
