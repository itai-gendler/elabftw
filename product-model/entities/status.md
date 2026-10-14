---
{
  "relations": [
    {
      "entity": "experiment",
      "verb": "labels",
      "cardinality": "one-to-many"
    },
    {
      "entity": "resource",
      "verb": "labels",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractStatus.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/ExperimentsStatus.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/ItemsStatus.php"
    }
  ]
}
---

# Status

A team-defined state an experiment or resource can show, such as Running, Success, Need to be redone or Fail, the four every new team starts with for experiments.

## Information kept

- **Title** — the name shown on entries
- **Color** — the color it is shown in
- **Private** — whether it stays within its team; a status that is not private is also offered to other teams
- **Applies to** — whether it is an experiment status or a resource status

## States

### Normal

Offered when choosing an entry's status.

### Deleted

No longer offered; entries keep showing it.
