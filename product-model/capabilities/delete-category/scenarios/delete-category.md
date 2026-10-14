---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User deletes a category",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "category",
          "effect": "reads",
          "facts": [
            "Title"
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
      "text": "The Product stops offering the category",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "category",
          "effect": "changes",
          "from": "Normal",
          "to": "Deleted",
          "facts": []
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

# Delete a category

## Trigger

A project ended.

## Outcome

The category is no longer offered; entries in it keep it.
