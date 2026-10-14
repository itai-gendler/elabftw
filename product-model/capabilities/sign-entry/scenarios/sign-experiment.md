---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Signature, picks a meaning and enters their passphrase",
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
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    },
    {
      "text": "The Product attaches a signature archive as an immutable archived file and adds a signature comment",
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
        "web": {
          "place": "web::signed-in::experiment"
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
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    }
  ]
}
---

# Sign an experiment

## Trigger

The User approves or reviews an experiment.

## Outcome

The experiment shows “Signed by” the User with the meaning as a comment that can never be edited or deleted; its archived files hold the data, the signature, the public key and a script to verify them with minisign.
