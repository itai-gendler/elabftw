---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "delete-storage-location"
    },
    {
      "type": "capability",
      "id": "add-container"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/StorageUnits.php"
    }
  ]
}
---

# A storage location that holds locations or containers is never deleted

A location is deleted only once it is empty; a location with a capacity accepts no container beyond it.
