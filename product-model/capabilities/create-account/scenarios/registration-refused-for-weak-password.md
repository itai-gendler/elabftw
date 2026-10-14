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
      "text": "The password misses the instance requirement, so the Product refuses and states it",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Minimum password length",
            "Password requirement"
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

# Refuse a registration with a weak password

## Trigger

Someone picks a password the instance does not accept.

## Outcome

No account is created.
