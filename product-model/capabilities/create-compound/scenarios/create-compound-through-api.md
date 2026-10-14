---
{
  "kind": "primary",
  "routes": {
    "api": "API"
  },
  "steps": [
    {
      "text": "The User sends a compound's name and identifiers",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "compound",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "api": {
          "place": "api"
        }
      }
    },
    {
      "text": "The Product adds the compound to the database",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "compound",
          "effect": "creates",
          "to": "Normal",
          "facts": [
            "Name",
            "CAS number",
            "PubChem CID",
            "SMILES",
            "InChI",
            "Molecular formula",
            "Hazards"
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

# Create a compound through the API

## Trigger

A script loads a chemical inventory.

## Outcome

The API answers 201 Created.
