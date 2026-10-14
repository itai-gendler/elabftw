---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Duplicate entry without copying files",
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
      "text": "The Product creates a Normal copy titled with an added “I”, keeping the original's content, steps and permissions with today's date",
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

# Duplicate an experiment

## Trigger

The experiment did not work the first time and the User starts a second iteration.

## Outcome

A new experiment owned by the User opens in edit mode, with the original's category, status, tags, text, custom fields, steps and links, today's date and a title ending in “I”.

## Edge cases

- The copy keeps the original's status.
- Custom fields marked to be blanked on duplicate start empty.
