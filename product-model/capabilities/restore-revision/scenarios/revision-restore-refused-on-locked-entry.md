---
{
  "kind": "validation",
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
      "text": "The experiment is locked, so the Product refuses",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": [
            "Locked"
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

# Refuse to restore a revision of a locked entry

## Trigger

Someone tries to restore an older text on a locked experiment, even its locker or an Admin.

## Outcome

The main text is unchanged and the User is told revisions of a locked item cannot be restored.
