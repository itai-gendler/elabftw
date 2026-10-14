---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "procurement-request",
      "effect": "creates"
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "holds",
          "entity": "team"
        },
        {
          "verb": "has",
          "entity": "team-membership"
        },
        {
          "verb": "holds",
          "entity": "user"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/ProcurementRequests.php"
    }
  ]
}
---

# Members of the team place orders

Anyone signed in to the team places an order for a procurable resource they can read.
