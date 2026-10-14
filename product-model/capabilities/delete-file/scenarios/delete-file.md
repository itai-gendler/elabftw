---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses to delete an attached file",
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
      "text": "The Product moves the attached file to Deleted",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "file",
          "effect": "changes",
          "from": "Normal",
          "to": "Deleted",
          "facts": []
        },
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Last changed by"
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

# Delete an attached file

## Trigger

The User attached the wrong file.

## Outcome

The file no longer appears among the experiment's attached files.
