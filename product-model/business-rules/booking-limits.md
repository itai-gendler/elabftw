---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "book-resource"
    },
    {
      "type": "capability",
      "id": "edit-booking"
    }
  ],
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

# Bookings respect the resource's booking rules

A booking ends after it starts, never overlaps another where overlapping is not allowed, stays within the maximum time per slot, the booking window and the maximum number of future bookings per person, and, for people who are not Admins, is not in the past unless the resource allows it. A recurring booking is created or changed only if every occurrence passes.
