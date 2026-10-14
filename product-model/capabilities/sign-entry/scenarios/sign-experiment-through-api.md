---
{
  "kind": "primary",
  "routes": {
    "api": "API"
  },
  "steps": [
    {
      "text": "The User sends the sign action with a meaning and their passphrase",
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
      "text": "The Product signs a JSON export of the experiment with the User's private key",
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
          "entity": "signature-key",
          "effect": "changes",
          "facts": [
            "Last used at"
          ]
        }
      ],
      "contexts": {
        "api": {
          "place": "api"
        }
      }
    },
    {
      "text": "The Product attaches the signature archive and adds a signature comment",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "file",
          "effect": "creates",
          "to": "Archived",
          "facts": [
            "Name",
            "Comment",
            "Immutable"
          ]
        },
        {
          "entity": "comment",
          "effect": "creates",
          "facts": [
            "Text",
            "Signature comment"
          ]
        }
      ],
      "contexts": {
        "api": {
          "place": "api"
        }
      }
    },
    {
      "text": "The Product counts the signature on the experiment and keeps the main text as a revision",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Signature count",
            "Last signed at"
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
        "api": {
          "place": "api"
        }
      }
    }
  ]
}
---

# Sign an experiment through the API

## Trigger

A review workflow signs experiments from a script.

## Outcome

The API returns the signed experiment.
