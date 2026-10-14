---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Visitor submits the registration form",
      "kind": "actor",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::public::register"
        }
      }
    },
    {
      "text": "Local registration is turned off, so the Product refuses",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Local registration"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::public::register"
        }
      }
    }
  ]
}
---

# Refuse registration when it is disabled

## Trigger

Someone tries to register on an instance that provisions accounts itself.

## Outcome

No account is created.
