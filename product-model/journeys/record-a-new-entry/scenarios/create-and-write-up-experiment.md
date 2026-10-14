---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Create and enters a title",
      "kind": "actor",
      "capability": "create-entry",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments"
        }
      }
    },
    {
      "text": "The Product creates a Normal experiment owned by the User",
      "kind": "product",
      "capability": "create-entry",
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
    },
    {
      "text": "The Product opens the new experiment in edit mode",
      "kind": "product",
      "capability": "create-entry",
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
      "text": "The User writes the main text and saves",
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
      "text": "The Product saves the main text and keeps it as a revision",
      "kind": "product",
      "capability": "edit-entry",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
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

# Create an experiment and write it up

## Trigger

The User starts recording new work.

## Outcome

The experiment holds the User's first write-up.
