---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User changes a category's name or colors",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "category",
          "effect": "reads",
          "facts": [
            "Title",
            "Color",
            "Text color"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments-categories"
        }
      }
    },
    {
      "text": "The Product saves the category",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "category",
          "effect": "changes",
          "facts": [
            "Title",
            "Color",
            "Text color"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments-categories"
        }
      }
    }
  ]
}
---

# Edit a category

## Trigger

A project was renamed.

## Outcome

Every entry in the category shows the new name and colors.
