---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Visitor enters their email and password",
      "kind": "actor",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::public::login"
        }
      }
    },
    {
      "text": "The password matches an account that is validated, unexpired and not archived",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Email",
            "Password",
            "Validated",
            "Valid until"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::public::login"
        }
      }
    },
    {
      "text": "The Visitor enters the code from their authenticator app",
      "kind": "actor",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::public::login"
        }
      }
    },
    {
      "text": "The code matches",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Two-factor authentication"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::public::login"
        }
      }
    },
    {
      "text": "The Product signs the person in and records the login",
      "kind": "product",
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

# Sign in with a password and a code

## Trigger

A member with two-factor authentication starts their day.

## Outcome

The person is signed in after the second factor.

## Edge cases

- Repeated wrong codes block further attempts for a while.
- A person the instance requires to use two-factor authentication who has not set it up is asked to set it up first.
