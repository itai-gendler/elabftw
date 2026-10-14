---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "event",
      "effect": "creates"
    }
  ],
  "permits": [
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "entity": "resource",
          "fact": "Bookable",
          "is": "Yes"
        },
        {
          "entity": "resource",
          "fact": "Booking permission",
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
          "entity": "resource",
          "fact": "Bookable",
          "is": "Yes"
        },
        {
          "entity": "resource",
          "fact": "Booking permission",
          "is": "Everyone with an account"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "has",
          "entity": "resource"
        },
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
          "entity": "resource",
          "fact": "Bookable",
          "is": "Yes"
        },
        {
          "entity": "resource",
          "fact": "Booking permission",
          "is": "Only members of the team"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "has",
          "entity": "resource"
        },
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
          "entity": "resource",
          "fact": "Bookable",
          "is": "Yes"
        },
        {
          "entity": "resource",
          "fact": "Booking permission",
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
          "verb": "has",
          "entity": "resource"
        },
        {
          "verb": "owns",
          "entity": "user"
        }
      ],
      "when": [
        {
          "entity": "resource",
          "fact": "Bookable",
          "is": "Yes"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Scheduler.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Elabftw/Permissions.php"
    }
  ]
}
---

# Only people its booking permission admits book a bookable resource

A resource is booked only while it is bookable, by its owner and by whoever its booking permission admits, on the same levels as Visibility.
