---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User turns off email notifications for new remarks",
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
      "text": "The Product saves the notification preferences on the account",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Notification preferences"
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

# Change notification settings

## Trigger

The User receives too many emails.

## Outcome

New comments notify the User only in the Product.
