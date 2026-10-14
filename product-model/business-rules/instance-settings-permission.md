---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "instance-settings",
      "effect": "changes",
      "facts": [
        "Timestamping authority",
        "Monthly timestamp limit",
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
      "target": "src/Models/Config.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/sysconfig.php"
    }
  ]
}
---

# Only a Sysadmin changes the instance settings

The Sysadmin panel is the only place the instance is configured.
