---
{
  "availability": [
    {
      "place": "web::signed-in"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractEntity.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Enums/BasePermissions.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/Check.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/user-guide/experiments.md"
    }
  ]
}
---

# Change an entry's visibility

Choose who may read an entry: a base level, widened by any teams, user groups and users added to it. Only the levels the instance allows are offered and accepted.
