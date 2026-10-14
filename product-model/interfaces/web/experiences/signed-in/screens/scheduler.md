---
{
  "entities": [
    {
      "entity": "event",
      "shows": [
        "Title",
        "Start",
        "End",
        "Recurrence",
        "Bound experiment",
        "Bound resource"
      ],
      "collects": [
        "Title",
        "Start",
        "End",
        "Recurrence"
      ]
    },
    {
      "entity": "resource",
      "shows": [
        "Title",
        "Bookable"
      ]
    },
    {
      "entity": "experiment",
      "shows": [
        "Title"
      ]
    }
  ],
  "entryPoints": [
    {
      "web": "/scheduler.php"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/scheduler.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/templates/scheduler.html"
    }
  ]
}
---

# Scheduler

The calendar of bookings on the resources the person can book or read, filterable by resource, category and owner.
