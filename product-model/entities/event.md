---
{
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

# Event

A booking: a reserved time slot on a bookable resource, shown in the scheduler. Each occurrence of a recurring booking is a booking of its own.

## Information kept

- **Title** — what the slot is for
- **Start** — when the slot starts
- **End** — when the slot ends, never before its start
- **Recurrence** — for a recurring booking, its rule: daily, weekly or monthly, its interval, weekdays and end
- **Bound experiment** — an experiment the booking is bound to, if any
- **Bound resource** — another resource the booking is bound to, if any
