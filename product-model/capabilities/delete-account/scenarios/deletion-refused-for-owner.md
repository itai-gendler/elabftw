---
{
  "kind": "validation",
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
            "Name"
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
      "text": "The account still owns entries, templates or uploads, so the Product refuses",
      "kind": "condition",
      "actor": "sysadmin",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
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

# Refuse to delete an account that owns entries

## Trigger

Someone tries to delete an account with a record.

## Outcome

The account stays; archiving is the way to stop its use.
