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
      "text": "The account's validity date has passed, so the Product refuses and says an Admin can extend it",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Valid until"
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

# Refuse an expired account

## Trigger

A visiting scientist's access ran out.

## Outcome

Nobody is signed in.
