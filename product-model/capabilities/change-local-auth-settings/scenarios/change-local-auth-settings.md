---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Sysadmin sets whether people may register and the password length and requirement",
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
      "text": "The Product saves the local authentication settings",
      "kind": "product",
      "actor": "sysadmin",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "changes",
          "facts": [
            "Local registration",
            "Minimum password length",
            "Password requirement"
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

# Change local authentication settings

## Trigger

The institution tightens its password policy.

## Outcome

Passwords set from now on must meet the new requirement; existing ones stay valid.
