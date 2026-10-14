---
{
  "availability": [
    {
      "place": "web::signed-in"
    },
    {
      "place": "api"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Compounds.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/PubChemImporter.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/user-guide/compounds.md"
    }
  ]
}
---

# Create a compound

Add a compound to the instance-wide compounds database: by hand, from PubChem by CAS number or CID, or from a molecule drawn in the chemical structure editor.
