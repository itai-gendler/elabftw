---
{
  "entities": [
    {
      "entity": "compound",
      "shows": [
        "Name",
        "SMILES",
        "CAS number"
      ]
    }
  ],
  "entryPoints": [
    {
      "web": "/chem-editor.php"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/chem-editor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/templates/chem-editor.html"
    }
  ]
}
---

# Chemical structure editor

Where a person draws a molecule to search the compounds database by structure or add it there.
