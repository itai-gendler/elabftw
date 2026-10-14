---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "comment",
      "effect": "removes"
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "writes",
          "entity": "user"
        }
      ],
      "when": [
        {
          "fact": "Signature comment",
          "is": "No"
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

# Only its author deletes a comment, and never a signature comment

People delete their own comments; the comments a signature leaves cannot be deleted by anyone.
