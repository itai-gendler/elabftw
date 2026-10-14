---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "procurement-request",
      "effect": "changes"
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
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/user-guide/resources.md"
    }
  ]
}
---

# Members of the team move its procurement requests along

The team's members review, receive, archive and cancel its procurement requests from the Team page; a cancelled request is kept for the record.
