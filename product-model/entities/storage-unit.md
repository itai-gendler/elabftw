---
{
  "domain": "inventory",
  "relations": [
    {
      "entity": "container",
      "verb": "stores",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/StorageUnits.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/inventory.md"
    }
  ]
}
---

# Storage location

A place in the inventory tree, such as a building, a room or a freezer shelf, where containers are stored.

## Information kept

- **Name** — its name
- **Parent** — the location it sits in, none for a root element
- **Capacity** — how many containers it can hold, if limited
