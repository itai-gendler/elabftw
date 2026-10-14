---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/ProcurementRequests.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Enums/ProcurementState.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/user-guide/resources.md"
    }
  ]
}
---

# Procurement request

An order placed for a procurable resource, followed by the team from request to reception.

## Information kept

- **Quantity ordered** — how many packs were ordered
- **Quantity received** — how many packs arrived
- **Comment** — what the requester wrote
- **Quote** — whether a quote is asked for

## States

### Pending

Placed and waiting for approval.

### Validated

Approved for ordering.

### Partially received

Part of the order arrived.

### Received

The whole order arrived.

### Archived

Closed and kept for the record.

### Cancelled

Withdrawn; kept for the record.
