---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User opens an experiment",
      "kind": "actor",
      "actor": "user",
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
            "Custom fields",
            "Visibility",
            "Can write",
            "Locked",
            "Timestamped",
            "eLabID",
            "Owner"
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

# Read an experiment

## Trigger

The User wants to read an experiment they can see in a list or were sent a link to.

## Outcome

The experiment page shows its content, steps, links, attached files, comments and permissions, in edit mode only when the User may change it.
