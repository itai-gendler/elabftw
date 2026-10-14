---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "apply-batch-action",
      "contexts": [
        {
          "place": "web::signed-in::admin-panel"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Batch.php"
    }
  ]
}
---

# Only Admins apply batch actions, and each entry still passes its own permissions

A batch action reaches only the entries of the Admin's team that match the chosen categories, statuses, tags or owners and that the Admin may act on.
