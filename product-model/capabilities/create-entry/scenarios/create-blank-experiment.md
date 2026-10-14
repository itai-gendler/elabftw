---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Create and enters a title",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments"
        }
      }
    },
    {
      "text": "The team lets the User create without a template",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": [
            "Allow users to create experiments",
            "Force experiment template use"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments"
        }
      }
    },
    {
      "text": "The Product creates a Normal experiment owned by the User, with the permissions their account sets as default",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Default visibility",
            "Default write permission",
            "Markdown editor"
          ]
        },
        {
          "entity": "experiment",
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
            "Team"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments"
        }
      }
    }
  ]
}
---

# Create a blank experiment

## Trigger

The User wants to record new work that follows no template.

## Outcome

A new Normal experiment titled as entered, “Untitled” if left empty, exists with today's date and the User's default visibility and write permission, and opens in edit mode.

## Edge cases

- A Custom ID is assigned only when the chosen category already has entries with one.
- The main text starts in Markdown when the User's account prefers the Markdown editor.
