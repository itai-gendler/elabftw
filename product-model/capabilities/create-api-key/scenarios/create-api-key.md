---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User names the key and chooses whether it may write",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::settings"
        }
      }
    },
    {
      "text": "The Product creates the API key, bound to the User and their current team, and shows its secret once",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "api-key",
          "effect": "creates",
          "facts": [
            "Name",
            "Can write",
            "Team"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::settings"
        }
      }
    }
  ]
}
---

# Create an API key

## Trigger

The User wants a script to work with their entries.

## Outcome

The key is listed in Settings; its secret is shown only at creation.
