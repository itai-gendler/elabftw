---
{
  "kind": "person",
  "acts": "external",
  "relations": [
    {
      "entity": "account",
      "verb": "uses",
      "cardinality": "one-to-one"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Users/Users.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/sysconfig.php"
    }
  ]
}
---

# Sysadmin

A person who administers the whole instance from the Sysadmin panel: its settings, timestamping, authentication and audit log. The first account created on an instance is a Sysadmin.
