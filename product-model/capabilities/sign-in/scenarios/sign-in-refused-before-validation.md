---
{
  "kind": "validation",
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
      "text": "The account is not validated yet, so the Product refuses and says an Admin must validate it",
      "kind": "condition",
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

# Refuse an account awaiting validation

## Trigger

A person who just registered tries to sign in before validation.

## Outcome

Nobody is signed in.
