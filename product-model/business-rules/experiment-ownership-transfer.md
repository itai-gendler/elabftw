---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "experiment",
      "effect": "changes",
      "facts": [
        "Owner",
        "Team"
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
    },
    {
      "actors": [
        "sysadmin"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractEntity.php"
    }
  ]
}
---

# Only an Admin of its team or a Sysadmin transfers a experiment to a new owner

Owning a experiment is not enough to hand it over: transferring it to another member, or to another team, takes an Admin of the team it belongs to or a Sysadmin. The new owner must belong to the destination team.
