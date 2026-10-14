---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Duplicate entry",
      "kind": "actor",
      "capability": "duplicate-entry",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    },
    {
      "text": "The Product creates a Normal copy of the experiment and opens it in edit mode",
      "kind": "product",
      "capability": "duplicate-entry",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "as": "original",
          "effect": "reads",
          "facts": [
            "Title",
            "Main text"
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
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    },
    {
      "text": "The User changes the title and the main text of the copy",
      "kind": "actor",
      "capability": "edit-entry",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    },
    {
      "text": "The Product saves the copy's new title and main text",
      "kind": "product",
      "capability": "edit-entry",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "as": "copy",
          "effect": "changes",
          "facts": [
            "Title",
            "Main text",
            "Last changed by"
          ]
        },
        {
          "entity": "revision",
          "effect": "creates",
          "facts": [
            "Main text",
            "Saved at"
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

# Duplicate an experiment and revise the copy

## Trigger

The first attempt did not work.

## Outcome

A second iteration exists beside the first, revised.
