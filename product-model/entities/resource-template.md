---
{
  "relations": [
    {
      "entity": "step",
      "verb": "has",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/ItemsTypes.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractTemplateEntity.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/user-guide/templates.md"
    }
  ]
}
---

# Resource template

A reusable starting point for resources, copied into each resource created from it like an experiment template, and also carrying the booking permission new resources start with.

## Information kept

- **Title** — the template's name, also the default title of entries created from it
- **Main text** — the body copied into each new entry
- **Category** — the category given to entries created from it
- **Status** — the status given to entries created from it
- **Tags** — the tags copied into each new entry
- **Custom fields** — the structured fields, with default values, copied into each new entry
- **Visibility** — who may read and use the template, on the same levels as an entry's Visibility
- **Can write** — who may change the template
- **Entry visibility** — the Visibility given to entries created from it
- **Entry write permission** — the Can write setting given to entries created from it
- **Lock down read permissions** — whether entries created from it get their Visibility locked down
- **Lock down write permissions** — whether entries created from it get their Can write setting locked down
- **Owner** — the person who owns the template
- **Team** — the team the template belongs to
- **Created from** — the entry or template it was created from, if any
- **Booking permission** — the booking permission given to resources created from it

## States

### Normal

Offered when creating entries.

### Deleted

No longer offered; entries created from it are unaffected.
