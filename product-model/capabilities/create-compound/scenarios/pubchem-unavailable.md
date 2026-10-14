---
{
  "kind": "edge",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User enters a CAS number and chooses Import",
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
      "text": "PubChem cannot be reached or knows no such compound, so the Product reports it and adds nothing",
      "kind": "condition",
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
    }
  ]
}
---

# Report PubChem unavailable

## Trigger

PubChem is down.

## Outcome

No compound is added.
