---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Sysadmin archives a person",
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
      "text": "The Product archives every membership of the person and signs them out",
      "kind": "product",
      "actor": "sysadmin",
      "entities": [
        {
          "entity": "team-membership",
          "effect": "changes",
          "from": "Active",
          "to": "Archived",
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

# Archive a user

## Trigger

A person left the institute.

## Outcome

The person can no longer sign in anywhere; their work stays.
