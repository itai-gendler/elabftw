---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "experiment",
      "effect": "reads"
    }
  ],
  "permits": [
    {
      "actors": [
        "visitor"
      ],
      "when": [
        {
          "fact": "Visibility",
          "is": "Everyone including anonymous users"
        },
        {
          "entity": "instance-settings",
          "fact": "Anonymous visitors",
          "is": "Allowed"
        }
      ]
    },
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "fact": "Visibility",
          "is": "Everyone including anonymous users"
        }
      ]
    },
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "fact": "Visibility",
          "is": "Everyone with an account"
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
          "fact": "Visibility",
          "is": "Only members of the team"
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
          "fact": "Visibility",
          "is": "Only owner and admins"
        },
        {
          "entity": "team-membership",
          "fact": "Role",
          "is": "Admin"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "user"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Elabftw/Permissions.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Enums/BasePermissions.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Elabftw/EntitySqlBuilder.php"
    }
  ]
}
---

# Only people its visibility admits read a experiment

A experiment is read by its owner and by whoever its Visibility admits: anonymous visitors when it is published to everyone and the instance lets them in, any signed-in person for “Everyone with an account”, members signed in to its team for “Only members of the team”, Admins of its team for “Only owner and admins”, and nobody else for “Only owner”. Teams, user groups and users added to the visibility can read it as well; an archived membership no longer counts. A share link carrying the experiment's access key also lets its holder read it.
