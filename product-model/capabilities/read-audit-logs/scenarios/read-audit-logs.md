---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Sysadmin opens the Audit Logs tab",
      "kind": "actor",
      "actor": "sysadmin",
      "entities": [
        {
          "entity": "audit-log-entry",
          "effect": "reads",
          "facts": [
            "Category",
            "Requester",
            "Target user",
            "Details",
            "When"
          ]
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

# Read the audit logs

## Trigger

The Sysadmin investigates who changed an account or a setting.

## Outcome

The most recent events are listed newest first, fifty at a time.
