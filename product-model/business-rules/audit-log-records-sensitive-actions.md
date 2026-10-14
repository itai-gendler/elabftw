---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "creates"
    },
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
        "Password",
        "Validated",
        "Last login",
        "Email",
        "Valid until"
      ]
    },
    {
      "type": "entity",
      "id": "team-membership",
      "effect": "creates"
    },
    {
      "type": "entity",
      "id": "team-membership",
      "effect": "changes"
    },
    {
      "type": "entity",
      "id": "team-membership",
      "effect": "removes"
    },
    {
      "type": "entity",
      "id": "api-key",
      "effect": "creates"
    },
    {
      "type": "entity",
      "id": "api-key",
      "effect": "removes"
    },
    {
      "type": "entity",
      "id": "signature-key",
      "effect": "creates"
    },
    {
      "type": "entity",
      "id": "instance-settings",
      "effect": "changes"
    },
    {
      "type": "entity",
      "id": "action-request",
      "effect": "creates"
    },
    {
      "type": "entity",
      "id": "experiment",
      "effect": "changes",
      "facts": [
        "Signature count"
      ]
    },
    {
      "type": "entity",
      "id": "account",
      "effect": "removes"
    },
    {
      "type": "entity",
      "id": "audit-log-entry"
    }
  ],
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
      "target": "src/Models/Config.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/traceability-and-auditability.md"
    }
  ]
}
---

# Sensitive actions are recorded in the instance audit log

Sign-ins, account creation, validation and password changes, team membership changes, API key creation and deletion, signature key creation, signatures, action requests and every instance setting change except the timestamp balance are recorded with who acted, on whom and when. Exports of more than twelve entries at once and imports are recorded too.
