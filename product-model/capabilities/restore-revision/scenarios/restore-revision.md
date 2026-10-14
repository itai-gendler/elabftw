---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User picks a revision and chooses Restore",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "revision",
          "effect": "reads",
          "facts": [
            "Main text",
            "Saved at"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::revisions"
        }
      }
    },
    {
      "text": "The Product puts that saved text back as the experiment's main text",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Main text"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::revisions"
        }
      }
    }
  ]
}
---

# Restore a revision

## Trigger

The User wants an earlier version of the text back.

## Outcome

The experiment's main text is the restored version and its changelog says which revision it was restored from.
