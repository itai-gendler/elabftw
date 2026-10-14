---
{
  "domain": "settings",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/ApiKeys.php"
    }
  ]
}
---

# API key

A credential that lets a person's scripts use the REST API as them, in one team.

## Information kept

- **Name** — a label chosen by its holder
- **Can write** — whether it may change things, or only read
- **Team** — the team its requests act in
- **Last used at** — when it was last used
