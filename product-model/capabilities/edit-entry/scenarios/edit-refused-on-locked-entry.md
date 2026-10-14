---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User tries to open a locked experiment in edit mode",
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
      "text": "Someone else locked the experiment and the User is not an Admin, so the page opens in view mode and changes are refused",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": [
            "Locked",
            "Locked by"
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

# Refuse to edit a locked entry

## Trigger

The User wants to change an experiment someone else has locked.

## Outcome

The experiment opens read-only and stays unchanged.
