---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User deletes one of their API keys",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "api-key",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::settings"
        }
      }
    },
    {
      "text": "The Product revokes the API key",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "api-key",
          "effect": "removes"
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

# Delete an API key

## Trigger

A script is retired or its key leaked.

## Outcome

Requests with that key are refused from now on.
