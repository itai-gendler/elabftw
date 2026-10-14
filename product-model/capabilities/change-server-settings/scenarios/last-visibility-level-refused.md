---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Sysadmin turns off the last allowed visibility level",
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
      "text": "At least one level must stay allowed, so the Product refuses",
      "kind": "condition",
      "actor": "sysadmin",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Allowed visibility levels"
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

# Refuse to disallow the last visibility level

## Trigger

The Sysadmin tries to disallow every level.

## Outcome

The level stays allowed.
