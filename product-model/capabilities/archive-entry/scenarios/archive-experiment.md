---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Archive",
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
      "text": "The Product archives the experiment and locks it, recording the User as its locker",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "changes",
          "from": "Normal",
          "to": "Archived",
          "facts": [
            "Locked",
            "Locked by",
            "Last changed by"
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

# Archive an experiment

## Trigger

The User tidies their workspace by putting away an experiment they no longer work on.

## Outcome

The experiment is Archived and locked: it appears only when archived entries are listed, and accepts no change but being unarchived.

## Edge cases

- An experiment someone else already locked keeps that person as its locker.
