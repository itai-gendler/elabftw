---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User deletes a compound",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "compound",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::compounds"
        }
      }
    },
    {
      "text": "An entry or template refers to the compound, so the Product refuses",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "compound",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::compounds"
        }
      }
    }
  ]
}
---

# Refuse to delete a linked compound

## Trigger

Someone tries to delete a compound in use.

## Outcome

The compound stays.
