---
{
  "kind": "primary",
  "routes": {
    "api": "API"
  },
  "steps": [
    {
      "text": "The User, an Admin, sends the update-owner action with the new owner and team",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "api": {
          "place": "api"
        }
      }
    },
    {
      "text": "The Product makes that person the experiment's owner in that team",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        },
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Owner",
            "Team",
            "Last changed by"
          ]
        }
      ],
      "contexts": {
        "api": {
          "place": "api"
        }
      }
    }
  ]
}
---

# Transfer ownership through the API

## Trigger

An Admin reassigns the entries of a departing member by script.

## Outcome

The API answers with no content.
