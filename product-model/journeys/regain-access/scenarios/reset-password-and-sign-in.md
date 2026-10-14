---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Visitor asks for a reset link and follows it",
      "kind": "actor",
      "capability": "recover-password",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::public::login"
        }
      }
    },
    {
      "text": "The Visitor enters a new password",
      "kind": "actor",
      "capability": "recover-password",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::public::reset-password"
        }
      }
    },
    {
      "text": "The Product sets the new password and returns the Visitor to the sign-in page",
      "kind": "product",
      "capability": "recover-password",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Password"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::public::reset-password"
        }
      }
    },
    {
      "text": "The Visitor signs in with the new password",
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
      "text": "The Product signs the person in",
      "kind": "product",
      "capability": "sign-in",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Last login"
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

# Reset the password and sign in

## Trigger

A person forgot their password.

## Outcome

The person is signed in again.
