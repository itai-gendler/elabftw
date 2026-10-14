---
{
  "relations": [
    {
      "entity": "experiment",
      "verb": "groups",
      "cardinality": "one-to-many"
    },
    {
      "entity": "resource",
      "verb": "groups",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/ExperimentsCategories.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/ResourcesCategories.php"
    }
  ]
}
---

# Category

A team-defined grouping for experiments or resources, such as a project or a kind of material, which also scopes Custom IDs.

## Information kept

- **Title** — the name shown on entries
- **Color** — the background color it is shown in
- **Text color** — the color of its label text
- **Private** — whether it stays within its team
- **Applies to** — whether it is an experiment category or a resource category

## States

### Normal

Offered when choosing an entry's category.

### Deleted

No longer offered; entries keep showing it.
