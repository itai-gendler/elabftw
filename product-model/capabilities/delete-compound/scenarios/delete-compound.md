---
{
  "kind": "primary",
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
      "text": "The Product removes the compound from the database",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "compound",
          "effect": "changes",
          "from": "Normal",
          "to": "Deleted",
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

# Delete a compound

## Trigger

A compound was added by mistake.

## Outcome

The compound is no longer listed.
