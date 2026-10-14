---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "export-request",
      "effect": "removes"
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "requests",
          "entity": "user"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Make/Exports.php"
    }
  ]
}
---

# Only the person who requested an export deletes it

Exports are private to their requester, who alone lists, downloads and deletes them.
