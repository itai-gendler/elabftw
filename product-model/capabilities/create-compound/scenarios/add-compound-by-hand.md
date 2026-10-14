---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Add compound and enters at least a name",
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
        "web": {
          "place": "web::signed-in::compounds"
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
        "web": {
          "place": "web::signed-in::compounds"
        }
      }
    }
  ]
}
---

# Add a compound by hand

## Trigger

The lab synthesized a new compound.

## Outcome

The compound is listed for everyone on the instance.
