---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "tag",
      "effect": "changes",
      "facts": [
        "Name"
      ]
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

# Only an Admin renames a team tag

Renaming a tag changes it on every entry, so only Admins do it, from the tag manager.
