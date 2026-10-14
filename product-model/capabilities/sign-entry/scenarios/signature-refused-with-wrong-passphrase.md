---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Signature and enters a passphrase",
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
      "text": "The passphrase does not unlock the User's private key, so the Product refuses and signs nothing",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "signature-key",
          "effect": "reads",
          "facts": [
            "Private key"
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

# Refuse a signature with a wrong passphrase

## Trigger

The User mistypes their passphrase.

## Outcome

No signature, archive or comment is created.
