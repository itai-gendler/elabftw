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

# Sign in with a password

## Trigger

A member starts their working day.

## Outcome

The person is signed in to their team and lands on their chosen start page.

## Edge cases

- A person in several teams picks which one to enter.
- Too many failed attempts in a short time lock further attempts for a while.
