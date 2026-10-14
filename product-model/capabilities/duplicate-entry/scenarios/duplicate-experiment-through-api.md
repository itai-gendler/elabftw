---
{
  "kind": "primary",
  "routes": {
    "api": "API"
  },
  "steps": [
    {
      "text": "The User sends the duplicate action",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "api": {
          "place": "api"
        }
      }
    },
    {
      "text": "The Product creates a Normal copy of the experiment",
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
        "api": {
          "place": "api"
        }
      }
    }
  ]
}
---

# Duplicate an experiment through the API

## Trigger

A script starts the next run of a protocol.

## Outcome

The API answers 201 Created with the copy's address.
