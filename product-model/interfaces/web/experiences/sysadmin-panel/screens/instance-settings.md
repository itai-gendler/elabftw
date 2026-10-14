---
{
  "entities": [
    {
      "entity": "instance-settings",
      "shows": [
        "Timestamping authority",
        "Monthly timestamp limit",
        "Timestamp balance",
        "Blockchain timestamping",
        "Allowed visibility levels",
        "Anonymous visitors",
        "Allow Admins to add existing users to their team",
        "Allow Admins to archive users",
        "Maximum revisions",
        "Minimum characters for a revision",
        "Days between revisions",
        "Local registration",
        "Minimum password length",
        "Password requirement",
        "Admin validation",
        "Enforce two-factor authentication",
        "Admins can create local accounts",
        "Allow users to change identity",
        "Restrict compounds editing",
        "Restrict inventory locations editing"
      ]
    },
    {
      "entity": "audit-log-entry",
      "shows": [
        "Category",
        "Requester",
        "Target user",
        "Details",
        "When"
      ]
    },
    {
      "entity": "team",
      "shows": [
        "Name"
      ],
      "collects": [
        "Name"
      ]
    },
    {
      "entity": "account",
      "shows": [
        "Name",
        "Email"
      ]
    }
  ],
  "entryPoints": [
    {
      "web": "/sysconfig.php"
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
      "target": "src/templates/sysconfig.html"
    }
  ]
}
---

# Instance settings

The Sysadmin panel's single page, with its Server, Security, Timestamp, Local auth and Audit Logs tabs among others.
