---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User enters a CAS number or a PubChem CID and chooses Import",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::compounds"
        }
      }
    },
    {
      "text": "The Product fetches the compound from PubChem and adds it to the database",
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
        "web": {
          "place": "web::signed-in::compounds"
        }
      }
    }
  ]
}
---

# Import a compound from PubChem

## Trigger

The User needs a known chemical in the database.

## Outcome

The compound is listed for everyone on the instance.
