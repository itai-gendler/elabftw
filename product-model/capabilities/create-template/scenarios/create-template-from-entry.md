---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Create template from entry",
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
      "text": "The Product creates a template from the experiment, copying its content and steps",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": [
            "Title",
            "Date",
            "Main text",
            "Custom ID",
            "Category",
            "Status",
            "Tags",
            "Custom fields",
            "eLabID",
            "Owner",
            "Visibility",
            "Can write"
          ]
        },
        {
          "entity": "experiment-template",
          "effect": "creates",
          "facts": [
            "Title",
            "Main text",
            "Visibility",
            "Can write",
            "Entry visibility",
            "Entry write permission",
            "Lock down read permissions",
            "Lock down write permissions",
            "Owner",
            "Team",
            "Category",
            "Status",
            "Tags",
            "Custom fields",
            "Created from"
          ],
          "to": "Normal"
        },
        {
          "entity": "step",
          "effect": "creates",
          "to": "Unfinished",
          "facts": [
            "Text",
            "Deadline",
            "Locked"
          ],
          "with": "experiment-template"
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

# Create a template from an entry

## Trigger

A successful experiment should become the team's standard procedure.

## Outcome

A new experiment template carries the experiment's content; results and identifiers specific to the original still need removing.
