---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "event",
      "effect": "changes"
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "books",
          "entity": "user"
        }
      ]
    },
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
      "target": "src/Models/Scheduler.php"
    }
  ]
}
---

# Only its booker or an Admin of its team changes a booking

People change their own bookings; Admins of the team the booking was made in change anyone's.
