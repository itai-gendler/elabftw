---
{
  "domain": "admin-panel",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Users2Teams.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/UserArchiver.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/TeamsHelper.php"
    }
  ]
}
---

# Team membership

A person's place in one team. A person can belong to several teams, with a different role and archive status in each.

## Information kept

- **Role** — User or Admin; the first member of a team becomes its Admin

## States

### Active

The person works in the team and can sign in to it.

### Archived

The person can no longer sign in to the team or use API keys bound to it; their past work stays visible.
