---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User tries to change a comment",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "comment",
          "effect": "reads",
          "facts": [
            "Text"
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
      "text": "The comment records a signature, so the Product refuses",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "comment",
          "effect": "reads",
          "facts": [
            "Signature comment"
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

# Refuse to edit a signature comment

## Trigger

Someone tries to alter the comment a signature left.

## Outcome

The comment is unchanged.
