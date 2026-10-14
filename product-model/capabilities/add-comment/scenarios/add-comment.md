---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User writes a remark and submits it",
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
      "text": "The Product adds the comment and notifies the experiment's owner and everyone who already commented, except the User",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "comment",
          "effect": "creates",
          "facts": [
            "Text",
            "Signature comment"
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

# Add a comment

## Trigger

The User wants to discuss an experiment with its owner.

## Outcome

The comment appears on the experiment and the owner and earlier commenters receive a notification.

## Edge cases

- Each person is notified once, however many comments they wrote.
