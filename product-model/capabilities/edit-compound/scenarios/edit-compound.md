---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User changes a compound's properties or hazards",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "compound",
          "effect": "reads",
          "facts": [
            "Name",
            "Hazards"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::compounds"
        }
      }
    },
    {
      "text": "The Product saves the compound",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "compound",
          "effect": "changes",
          "facts": [
            "Name",
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

# Edit a compound

## Trigger

A compound's hazard classification was missing.

## Outcome

Every entry referring to it shows the updated compound.
