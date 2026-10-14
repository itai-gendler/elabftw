---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "import-file",
      "contexts": [
        {
          "place": "web::signed-in::profile"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Import/Handler.php"
    }
  ]
}
---

# Only an Admin of the team imports entries owned by someone else

An import creates entries owned by the importer in their current team, unless an Admin of that team picks another member of it as owner.
