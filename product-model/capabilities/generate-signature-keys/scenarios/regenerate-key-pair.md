---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User already has an active key pair",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "signature-key",
          "as": "previous",
          "effect": "reads",
          "facts": [
            "Public key"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::settings"
        }
      }
    },
    {
      "text": "The User enters a new passphrase and chooses Regenerate signature keys",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::settings"
        }
      }
    },
    {
      "text": "The Product archives the current key pair and creates a new active one",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "signature-key",
          "as": "previous",
          "effect": "changes",
          "from": "Active",
          "to": "Archived",
          "facts": []
        },
        {
          "entity": "signature-key",
          "as": "current",
          "effect": "creates",
          "to": "Active",
          "facts": [
            "Public key",
            "Private key"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::settings"
        }
      }
    }
  ]
}
---

# Regenerate the key pair

## Trigger

The User forgot their passphrase or suspects their key is compromised.

## Outcome

Only the new key pair signs from now on; signatures made with the old one remain verifiable with its public key.
