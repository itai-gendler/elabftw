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
      "text": "The person's membership is archived, so the Product refuses",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "team-membership",
          "effect": "reads",
          "facts": []
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

# Refuse an archived member

## Trigger

A former member tries to sign in.

## Outcome

Nobody is signed in.
