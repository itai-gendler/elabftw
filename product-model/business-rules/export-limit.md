---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "request-export",
      "contexts": [
        {
          "place": "web::signed-in::profile"
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
      "target": "src/Make/Exports.php"
    }
  ]
}
---

# A person keeps at most six exports

A new export is refused while the person already keeps six; deleting one makes room.
