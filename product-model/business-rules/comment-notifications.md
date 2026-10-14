---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "add-comment",
      "contexts": [
        {
          "place": "web::signed-in"
        },
        {
          "place": "api"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Comments.php"
    }
  ]
}
---

# A new comment notifies the entry's owner and everyone who already commented, except its author

Each recipient is notified once per comment, by email too unless they turned that off.
