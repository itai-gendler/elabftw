---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Delete entry",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    },
    {
      "text": "The Product moves the experiment and its attached files to Deleted and releases its Custom ID",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "changes",
          "from": "Normal",
          "to": "Deleted",
          "facts": [
            "Custom ID",
            "Last changed by"
          ]
        },
        {
          "entity": "file",
          "effect": "changes",
          "from": "Normal",
          "to": "Deleted",
          "facts": []
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

# Delete an experiment

## Trigger

The User removes an experiment that is no longer relevant.

## Outcome

The experiment is Deleted: listed only when deleted entries are shown, read-only, and its Custom ID is free for another entry.

## Edge cases

- The experiment is also removed from everyone's pinned entries.
