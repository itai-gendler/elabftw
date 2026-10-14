---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User changes the main text and saves",
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
      "text": "The Product saves the main text, keeps it as a new revision and records who changed it",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Main text",
            "Last changed by"
          ]
        },
        {
          "entity": "revision",
          "effect": "creates",
          "facts": [
            "Main text",
            "Saved at"
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

# Edit the main text

## Trigger

The User writes up their procedure and results.

## Outcome

The experiment shows the new main text, the changelog points to the revisions, and the revisions page lists the new version.

## Edge cases

- A change smaller than the instance's minimum number of characters is not kept as a revision unless the entry has none yet or its last change is older than the instance's days between revisions.
- Revisions beyond the instance maximum are discarded, oldest first.
