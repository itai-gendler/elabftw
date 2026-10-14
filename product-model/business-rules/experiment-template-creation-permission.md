---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "experiment-template",
      "effect": "creates"
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
          "entity": "team",
          "fact": "Allow users to create experiments templates",
          "is": "On"
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
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Teams.php"
    }
  ]
}
---

# Members create an experiment template only while their team allows it; Admins always may

Members who are not Admins can create an experiment template only while the team's “Allow users to create experiments templates” setting is on.
