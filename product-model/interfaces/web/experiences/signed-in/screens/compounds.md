---
{
  "entities": [
    {
      "entity": "compound",
      "shows": [
        "Name",
        "CAS number",
        "PubChem CID",
        "SMILES",
        "InChI",
        "Molecular formula",
        "Hazards"
      ],
      "collects": [
        "Name",
        "CAS number",
        "PubChem CID",
        "SMILES",
        "InChI",
        "Molecular formula",
        "Hazards"
      ]
    },
    {
      "entity": "resource-template",
      "shows": [
        "Title"
      ]
    },
    {
      "entity": "resource",
      "shows": [
        "Title"
      ]
    }
  ],
  "entryPoints": [
    {
      "web": "/compounds.php"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/compounds.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controllers/CompoundsController.php"
    }
  ]
}
---

# Compounds

The instance-wide compounds database.
