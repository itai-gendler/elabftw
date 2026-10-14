---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "timestamp-entry",
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
      "target": "src/Make/AbstractMakeTimestamp.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractConcreteEntity.php"
    }
  ]
}
---

# The instance makes no more timestamps in a sliding month than its monthly limit

Timestamps made anywhere on the instance count together against its Monthly timestamp limit over the past month; a limit of 0 means no limit.
