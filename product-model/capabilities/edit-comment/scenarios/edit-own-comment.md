---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User changes the text of their comment",
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
      "text": "The Product saves the new text",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "comment",
          "effect": "changes",
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
    }
  ]
}
---

# Edit one's own comment

## Trigger

The User corrects what they wrote.

## Outcome

The comment shows the new text.
