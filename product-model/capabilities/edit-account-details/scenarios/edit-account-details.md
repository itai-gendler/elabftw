---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User changes their name or email and confirms with their password",
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
      "text": "The Product saves the account details",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Name",
            "Email",
            "ORCID"
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

# Edit account details

## Trigger

The User changed their name.

## Outcome

The account shows the new details; an email change is recorded in the audit log.
