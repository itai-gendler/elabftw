---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses to unpin a pinned experiment",
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
      "text": "The Product removes the experiment from the User's pinned entries",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Pinned entries"
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

# Unpin an experiment

## Trigger

An experiment is finished.

## Outcome

The experiment takes its ordinary place in the list.
