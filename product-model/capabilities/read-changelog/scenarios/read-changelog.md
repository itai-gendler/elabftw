---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User opens the experiment's changelog",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": [
            "Title"
          ]
        },
        {
          "entity": "changelog-entry",
          "effect": "reads",
          "facts": [
            "Who",
            "What changed",
            "New value",
            "When"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::changelog"
        }
      }
    }
  ]
}
---

# Read an experiment's changelog

## Trigger

The User wants to know who changed what on an experiment.

## Outcome

The changelog lists each change, newest first, from its creation onwards.
