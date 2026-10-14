---
{
  "kind": "edge",
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
      "text": "The authority does not return a valid token, so the Product reports the error and attaches nothing",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Timestamping authority"
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

# Fail when the authority gives no token

## Trigger

The Time Stamping Authority is unreachable or rejects the request.

## Outcome

The experiment is not marked timestamped and no archive is attached.
