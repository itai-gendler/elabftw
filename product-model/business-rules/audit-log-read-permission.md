---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "audit-log-entry",
      "effect": "reads"
    }
  ],
  "permits": [
    {
      "actors": [
        "sysadmin"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/sysconfig.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AuditLogs.php"
    }
  ]
}
---

# Only a Sysadmin reads the audit log

Audit log entries are shown only on the Sysadmin panel.
