---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "event",
      "effect": "removes"
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

# Only its booker or an Admin of its team cancels a booking

People cancel their own bookings within the resource's cancellation rules; Admins of the team cancel any booking at any time.
