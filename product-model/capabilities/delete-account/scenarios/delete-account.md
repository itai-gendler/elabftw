---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Sysadmin deletes an account",
      "kind": "actor",
      "actor": "sysadmin",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Name",
            "Email"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::sysadmin-panel::instance-settings"
        }
      }
    },
    {
      "text": "The Product removes the account and its memberships",
      "kind": "product",
      "actor": "sysadmin",
      "entities": [
        {
          "entity": "account",
          "effect": "removes"
        },
        {
          "entity": "team-membership",
          "effect": "removes",
          "from": "Active"
        }
      ],
      "contexts": {
        "web": {
          "place": "web::sysadmin-panel::instance-settings"
        }
      }
    }
  ]
}
---

# Delete an account

## Trigger

An account was registered by mistake.

## Outcome

The account is gone; the audit log records the deletion.
