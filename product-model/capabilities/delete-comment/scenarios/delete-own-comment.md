---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses to delete their comment",
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
      "text": "The Product removes the comment",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "comment",
          "effect": "removes"
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

# Delete one's own comment

## Trigger

The User withdraws a remark.

## Outcome

The comment is gone from the experiment.
