---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses RFC 3161 timestamping",
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
      "text": "The instance is under its monthly timestamp limit",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Monthly timestamp limit"
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
      "text": "The Product exports the experiment, has the export's fingerprint certified by the configured authority, and attaches data and token as an immutable archived file",
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
            "Owner"
          ]
        },
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Timestamping authority"
          ]
        },
        {
          "entity": "file",
          "effect": "creates",
          "to": "Archived",
          "facts": [
            "Name",
            "Comment",
            "Immutable"
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
      "text": "The Product marks the experiment timestamped at the token's time, counts down the timestamp balance and keeps the main text as a revision",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Timestamped",
            "Timestamped at"
          ]
        },
        {
          "entity": "instance-settings",
          "effect": "changes",
          "facts": [
            "Timestamp balance"
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

# Timestamp an experiment

## Trigger

The User needs proof of when their results were recorded.

## Outcome

The experiment shows who timestamped it and when; a ZIP archive holding the exported data and the authority's token sits among its archived attached files, ready to verify with openssl.

## Decision points

### Which export is timestamped?

Does the instance stamp a PDF with Keeex?

- Keeex is enabled → a PDF/A export, stamped by Keeex, is timestamped
- Keeex is not enabled → a full JSON export is timestamped

## Edge cases

- Changes made after the timestamp are not covered by the archive; timestamping again makes a new one.
- The timestamp balance is not counted below zero.
