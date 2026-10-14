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
          "place": "web::signed-in::resource"
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
          "place": "web::signed-in::resource"
        }
      }
    },
    {
      "text": "The Product exports the resource, has the export's fingerprint certified by the configured authority, and attaches data and token as an immutable archived file",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
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
          "place": "web::signed-in::resource"
        }
      }
    },
    {
      "text": "The Product marks the resource timestamped at the token's time, counts down the timestamp balance and keeps the main text as a revision",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
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
          "place": "web::signed-in::resource"
        }
      }
    }
  ]
}
---

# Timestamp a resource

## Trigger

The User certifies the state of a protocol or a material record.

## Outcome

The resource carries a timestamp archive and shows when it was timestamped.
