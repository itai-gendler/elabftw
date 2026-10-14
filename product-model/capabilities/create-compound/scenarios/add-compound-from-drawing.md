---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User draws a molecule and chooses Add to compounds database",
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
          "place": "web::signed-in::chemical-structure-editor"
        }
      }
    },
    {
      "text": "The Product adds the drawn structure as a compound",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "compound",
          "effect": "creates",
          "to": "Normal",
          "facts": [
            "Name",
            "SMILES",
            "InChI",
            "Molecular formula"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::chemical-structure-editor"
        }
      }
    }
  ]
}
---

# Add a compound from a drawing

## Trigger

The User sketched a structure.

## Outcome

The compound is in the database with its structure.
