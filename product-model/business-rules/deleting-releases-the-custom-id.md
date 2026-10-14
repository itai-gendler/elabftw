---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "delete-entry"
    },
    {
      "type": "capability",
      "id": "restore-entry"
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

# Deleting an entry releases its Custom ID, and restoring it does not take the number back

A deleted entry gives up its Custom ID so another entry of the category can use it; a restored entry has none until one is set again.
