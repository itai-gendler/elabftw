---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "cancel-booking",
      "contexts": [
        {
          "place": "web::signed-in::scheduler"
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

# Only Admins cancel a booking the resource does not let be cancelled, or one starting sooner than its notice

For people who are not Admins, a booking is cancelled only while its resource is cancellable and at least its minimum cancellation notice before it starts; a past booking only within a few minutes of its creation.
