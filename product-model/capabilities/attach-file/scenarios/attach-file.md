---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User drops a file onto the experiment",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    },
    {
      "text": "The Product attaches the file to the experiment",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "file",
          "effect": "creates",
          "to": "Normal",
          "facts": [
            "Name",
            "Comment",
            "Immutable"
          ]
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

# Attach a file

## Trigger

The User adds raw data, a gel image or a protocol PDF.

## Outcome

The file is listed among the experiment's attached files.
