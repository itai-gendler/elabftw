---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "delete-compound",
      "contexts": [
        {
          "place": "web::signed-in::compounds"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Compounds.php"
    }
  ]
}
---

# A compound an entry or template refers to is never deleted

Deleting a compound is refused while any experiment, resource or template links to it.
