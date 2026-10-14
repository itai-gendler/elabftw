---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Sysadmin picks a timestamping authority and sets the monthly limit",
      "kind": "actor",
      "actor": "sysadmin",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::sysadmin-panel::instance-settings"
        }
      }
    },
    {
      "text": "The Product saves the timestamp settings",
      "kind": "product",
      "actor": "sysadmin",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "changes",
          "facts": [
            "Timestamping authority",
            "Monthly timestamp limit",
            "Blockchain timestamping"
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

# Change timestamp settings

## Trigger

The institution signs a contract with a qualified authority.

## Outcome

Timestamps made from now on use the new authority and limit.
