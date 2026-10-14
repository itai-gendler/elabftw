---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "edit-entry"
    },
    {
      "type": "capability",
      "id": "change-entry-status"
    },
    {
      "type": "capability",
      "id": "lock-entry"
    },
    {
      "type": "capability",
      "id": "timestamp-entry"
    },
    {
      "type": "capability",
      "id": "sign-entry"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractEntity.php"
    }
  ]
}
---

# Archived and deleted entries accept no change but leaving that state

An archived experiment or resource accepts only being unarchived, and a deleted one only being restored: editing, changing its status, locking, timestamping or signing it is refused until it is Normal again.
