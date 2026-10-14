---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses to delete a timestamp or signature archive",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "file",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    },
    {
      "text": "The attached file is immutable, so the Product refuses",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "file",
          "effect": "reads",
          "facts": [
            "Immutable"
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

# Refuse to delete a timestamp or signature archive

## Trigger

Someone tries to remove the proof a timestamp or signature left.

## Outcome

The archive stays attached.
