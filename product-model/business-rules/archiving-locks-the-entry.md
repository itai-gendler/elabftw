---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "archive-entry"
    },
    {
      "type": "capability",
      "id": "unarchive-entry"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractEntity.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Elabftw/Permissions.php"
    }
  ]
}
---

# Archiving an entry locks it

Archiving locks the entry in the archiver's name unless it is already locked, so an archived entry stays read-only.
