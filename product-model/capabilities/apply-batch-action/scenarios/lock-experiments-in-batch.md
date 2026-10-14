---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User, an Admin, picks a category and the Lock action",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "category",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::admin-panel"
        }
      }
    },
    {
      "text": "The Product locks every experiment of the category the User may change",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "category",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Locked",
            "Locked by"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::admin-panel"
        }
      }
    }
  ]
}
---

# Lock experiments in batch

## Trigger

The project closes and its experiments must be frozen.

## Outcome

The User is told how many entries were processed.

## Edge cases

- Each entry is processed only if the User may perform the action on it.
