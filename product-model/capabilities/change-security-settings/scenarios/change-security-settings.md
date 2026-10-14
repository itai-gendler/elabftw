---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Sysadmin turns Admin validation on or off",
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
      "text": "The Product saves the security settings",
      "kind": "product",
      "actor": "sysadmin",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "changes",
          "facts": [
            "Admin validation"
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

# Change security settings

## Trigger

The institution provisions people it already trusts.

## Outcome

People who register from now on are validated, or not, accordingly.
