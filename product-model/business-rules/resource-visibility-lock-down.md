---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "resource",
      "effect": "changes",
      "facts": [
        "Visibility"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "fact": "Visibility locked down",
          "is": "No"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "keeps",
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
      ],
      "when": [
        {
          "entity": "team-membership",
          "fact": "Role",
          "is": "Admin"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractEntity.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/user-guide/templates.md"
    }
  ]
}
---

# Only an Admin changes the visibility of a resource whose visibility is locked down

A template can lock down the Visibility of the entries created from it; on such a resource, members cannot change it and Admins still can.
