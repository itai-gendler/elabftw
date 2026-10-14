---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User requests another export",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::profile"
        }
      }
    },
    {
      "text": "The User already keeps six exports, so the Product asks them to delete one first",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "export-request",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::profile"
        }
      }
    }
  ]
}
---

# Refuse an export over the limit

## Trigger

The User has many old exports.

## Outcome

No export is recorded.
