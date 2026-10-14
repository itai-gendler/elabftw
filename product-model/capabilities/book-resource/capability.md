---
{
  "availability": [
    {
      "place": "web::signed-in"
    },
    {
      "place": "api"
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
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/EventsRecurrence.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/user-guide/scheduler.md"
    }
  ]
}
---

# Book a resource

Reserve a time slot on a bookable resource, once or recurring, in the scheduler. Every occurrence is checked against the resource's booking rules before any is created.
