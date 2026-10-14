---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User opens a deleted experiment and chooses Restore entry",
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
      "text": "The Product returns the experiment and its attached files to Normal, without its former Custom ID",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "changes",
          "from": "Deleted",
          "to": "Normal",
          "facts": [
            "Last changed by"
          ]
        },
        {
          "entity": "file",
          "effect": "changes",
          "from": "Deleted",
          "to": "Normal",
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

# Restore an experiment

## Trigger

The User deleted an experiment by mistake.

## Outcome

The experiment is Normal, listed, editable within its permissions and exportable again; it has no Custom ID until one is set again.

## Edge cases

- An entry that was locked when deleted is still locked after restoring.
