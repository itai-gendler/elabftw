---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses to use two-factor authentication, scans the QR code and enters the code shown",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::settings"
        }
      }
    },
    {
      "text": "The code matches",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::settings"
        }
      }
    },
    {
      "text": "The Product turns on two-factor authentication for the account",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Two-factor authentication"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::settings"
        }
      }
    }
  ]
}
---

# Enable two-factor authentication

## Trigger

The User secures their account.

## Outcome

Signing in asks for a code from now on.
