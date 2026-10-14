---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User picks a language, an editor and the default visibility and write permission of new entries",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::settings"
        }
      }
    },
    {
      "text": "The Product saves them on the User's account",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Preferred language",
            "Markdown editor",
            "Default visibility",
            "Default write permission"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::settings"
        }
      }
    }
  ]
}
---

# Change general settings

## Trigger

The User wants their new entries shared with the team by default.

## Outcome

Entries the User creates without a template from now on start with these permissions, in the chosen editor.
