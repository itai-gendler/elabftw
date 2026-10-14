---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User enters a passphrase and chooses Generate",
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
      "text": "The Product creates an active key pair whose private key the passphrase protects",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "signature-key",
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

# Generate a first key pair

## Trigger

The User wants to sign entries.

## Outcome

The User can sign experiments and resources with the passphrase.
