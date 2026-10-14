---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User clicks a tag on the experiment and confirms its removal",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "tag",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        },
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
      "text": "The Product detaches the tag from the experiment and keeps the tag itself",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "tag",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Tags"
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

# Remove a tag

## Trigger

A tag no longer applies to the experiment.

## Outcome

The experiment no longer lists the tag; its changelog records the removal.
