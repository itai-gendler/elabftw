---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The instance lets anonymous visitors in",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Anonymous visitors"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::public::experiment"
        }
      }
    },
    {
      "text": "The Visitor opens an experiment published to everyone",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": [
            "Title",
            "Date",
            "Main text",
            "Status",
            "Category",
            "Tags",
            "eLabID",
            "Owner"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::public::experiment"
        }
      }
    }
  ]
}
---

# Read a public experiment anonymously

## Trigger

An anonymous visitor enters a team and opens one of its public experiments.

## Outcome

The visitor reads the experiment without being able to change it.

## Edge cases

- A share link carrying the entry's access key lets anyone holding it read that entry and its files.
