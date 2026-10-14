---
{
  "kind": "edge",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User opens an experiment that another person has open in edit mode",
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
      "text": "The Product refuses the User's changes and names who is editing",
      "kind": "condition",
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
    }
  ]
}
---

# Block changes while another person edits

## Trigger

Two people with write access work on the same experiment at once.

## Outcome

The User sees that the entry is being edited by the other person and changes nothing until that hold ends.

## Edge cases

- Choosing Override lock releases the other person's hold.
- A hold older than 42 minutes is ignored.
- Pinning and the share link stay available during the hold.
