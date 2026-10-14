---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "tag",
      "effect": "removes"
    }
  ],
  "permits": [
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
      "target": "src/Models/TeamTags.php"
    }
  ]
}
---

# Only an Admin deletes a team tag

Deleting a tag detaches it from every entry, so only Admins do it.
