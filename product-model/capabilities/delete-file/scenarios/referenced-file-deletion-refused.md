---
{
  "kind": "validation",
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
      "text": "The main text still refers to the file, so the Product asks the User to remove the reference first",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": [
            "Main text"
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

# Refuse to delete a file the main text uses

## Trigger

The User tries to delete an image shown in the main text.

## Outcome

The file stays attached.
