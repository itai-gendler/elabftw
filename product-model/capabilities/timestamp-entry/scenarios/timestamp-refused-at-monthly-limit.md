---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses RFC 3161 timestamping",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    },
    {
      "text": "The instance already made as many timestamps in the past month as its limit allows, so the Product refuses",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Monthly timestamp limit"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    }
  ]
}
---

# Refuse a timestamp at the monthly limit

## Trigger

The instance has used up its monthly timestamp allowance.

## Outcome

Nothing is timestamped and the User is told the monthly limit is reached.
