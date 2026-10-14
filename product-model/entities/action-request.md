---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/RequestActions.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Enums/RequestableAction.php"
    }
  ]
}
---

# Action request

A request, made on an experiment or resource, that another person archive, lock, review, sign or timestamp it.

## Information kept

- **Action** — Archive, Lock, Review, Sign or Timestamp
- **Requester** — who asked
- **Target user** — who is asked to act

## States

### Pending

Waiting for the target user, who is notified.

### Done

The target user performed the requested action on the entry.
