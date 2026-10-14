---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "experiment",
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
          "fact": "Allow users to create experiments",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/templates/create-new-modal.html"
    }
  ]
}
---

# Members create an experiment only while their team allows it; Admins always may

An experiment is created in the team its creator is signed in to. Members who are not Admins can create one, including by duplicating, only while the team's “Allow users to create experiments” setting is on.
