---
{
  "domain": "sysadmin-panel",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AuditLogs.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Enums/AuditCategory.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/AuditEvent/AbstractAuditEvent.php"
    }
  ]
}
---

# Audit log entry

One sensitive action recorded on the instance audit log, which only Sysadmins read: who acted, on whom, what happened and when.

## Information kept

- **Category** — the kind of event, such as Login, AccountCreated, PasswordChanged, Users2TeamsModified, ApiKeyCreated, ConfigModified, SignatureCreated or ActionRequested
- **Requester** — the person who performed the action
- **Target user** — the person the action concerned
- **Details** — a description of what changed
- **When** — the time of the action
