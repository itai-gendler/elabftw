---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User draws a molecule and chooses Search similar structures",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::chemical-structure-editor"
        }
      }
    },
    {
      "text": "The User reads the compounds that contain the drawn structure",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "compound",
          "effect": "reads",
          "facts": [
            "Name",
            "SMILES",
            "CAS number"
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

# Search similar structures

## Trigger

The User looks for every compound with a given ring system.

## Outcome

The matching compounds are listed.

## Edge cases

- Only compounds with a fingerprint can match; fingerprinting needs a SMILES representation.
