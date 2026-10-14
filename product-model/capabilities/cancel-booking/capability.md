---
{
  "availability": [
    {
      "place": "web::signed-in"
    }
  ],
  "domain": "scheduler",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Scheduler.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/user-guide/scheduler.md"
    }
  ]
}
---

# Cancel a booking

Remove a booking, optionally telling the team or the resource's other bookers why. The team's Admins are notified.
