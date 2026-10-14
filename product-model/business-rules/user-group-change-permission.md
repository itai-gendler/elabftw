---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "user-group",
      "effect": "changes"
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
      "target": "src/Models/TeamGroups.php"
    }
  ]
}
---

# Only an Admin of its team changes a user group

User groups are kept by a team and managed by its Admins; their members may come from any team.
