---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Blockchain timestamping",
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
      "text": "Blockchain timestamping is enabled and the instance is under its monthly limit",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Blockchain timestamping",
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
      "text": "The Product sends the fingerprint of the experiment's export to the Bloxberg blockchain and attaches data and certificate as an immutable archived file",
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
      "text": "The Product marks the experiment timestamped at the current server time",
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

# Timestamp an experiment on the blockchain

## Trigger

The User prefers a blockchain proof to a TSA token.

## Outcome

The experiment carries an archive with the exported data and the Bloxberg certificate PDF.

## Edge cases

- The author sent to Bloxberg is anonymized when the instance asks for it.
