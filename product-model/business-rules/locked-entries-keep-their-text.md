---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "restore-revision",
      "contexts": [
        {
          "place": "web::signed-in::revisions"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Revisions.php"
    }
  ]
}
---

# A revision is never restored on a locked entry

Restoring an earlier main text is refused while the entry is locked, whoever asks, even its locker or an Admin.
