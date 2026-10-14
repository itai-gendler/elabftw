---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Duplicate entry, copying files and linking the copy to the original",
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
      "text": "The Product creates a Normal copy with copies of the attached files and a link back to the original",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "as": "original",
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
          "entity": "experiment",
          "as": "copy",
          "effect": "creates",
          "to": "Normal",
          "facts": [
            "Title",
            "Date",
            "Main text",
            "Custom ID",
            "Category",
            "Status",
            "Tags",
            "Custom fields",
            "Visibility",
            "Can write",
            "Visibility locked down",
            "Can write locked down",
            "Locked",
            "Timestamped",
            "Signature count",
            "eLabID",
            "Owner",
            "Team",
            "Created from"
          ]
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
          "with": "copy"
        },
        {
          "entity": "file",
          "effect": "creates",
          "to": "Normal",
          "facts": [
            "Name",
            "Comment",
            "Immutable"
          ],
          "with": "copy"
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

# Duplicate an experiment with its files and a link

## Trigger

The User wants the new iteration to keep the data files and point to the first one.

## Outcome

The copy carries the files and links to the original experiment.
