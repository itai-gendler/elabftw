---
{
  "kind": "person",
  "acts": "external",
  "relations": [
    {
      "entity": "account",
      "verb": "uses",
      "cardinality": "one-to-one"
    },
    {
      "entity": "team-membership",
      "verb": "holds",
      "cardinality": "one-to-many"
    },
    {
      "entity": "experiment",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "resource",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "experiment-template",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "resource-template",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "experiment",
      "verb": "locks",
      "cardinality": "one-to-many"
    },
    {
      "entity": "resource",
      "verb": "locks",
      "cardinality": "one-to-many"
    },
    {
      "entity": "comment",
      "verb": "writes",
      "cardinality": "one-to-many"
    },
    {
      "entity": "signature-key",
      "verb": "holds",
      "cardinality": "one-to-many"
    },
    {
      "entity": "api-key",
      "verb": "holds",
      "cardinality": "one-to-many"
    },
    {
      "entity": "action-request",
      "verb": "requests",
      "cardinality": "one-to-many"
    },
    {
      "entity": "action-request",
      "verb": "receives",
      "cardinality": "one-to-many"
    },
    {
      "entity": "event",
      "verb": "books",
      "cardinality": "one-to-many"
    },
    {
      "entity": "export-request",
      "verb": "requests",
      "cardinality": "one-to-many"
    },
    {
      "entity": "to-do-item",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "procurement-request",
      "verb": "places",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Users/Users.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Enums/Usergroup.php"
    }
  ]
}
---

# User

A signed-in member of one or more teams who records experiments, keeps resources and works with templates. Whether they also administer a team is held by their team membership.

## Information kept

- **Can manage compounds** — whether a Sysadmin let the person edit the compounds database while the instance restricts it
- **Can manage inventory locations** — whether a Sysadmin let the person edit inventory locations while the instance restricts it
