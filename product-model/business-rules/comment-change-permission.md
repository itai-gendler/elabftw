---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "comment",
      "effect": "changes",
      "facts": [
        "Text"
      ]
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

# Only its author edits a comment, and never a signature comment

People edit their own comments; the comments a signature leaves cannot be edited by anyone.
