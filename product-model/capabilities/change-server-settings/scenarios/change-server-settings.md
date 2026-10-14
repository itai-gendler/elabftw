---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Sysadmin changes server settings such as the allowed visibility levels or how many text versions are kept",
      "kind": "actor",
      "actor": "sysadmin",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::sysadmin-panel::instance-settings"
        }
      }
    },
    {
      "text": "The Product saves each changed setting",
      "kind": "product",
      "actor": "sysadmin",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "changes",
          "facts": [
            "Allowed visibility levels",
            "Anonymous visitors",
            "Allow Admins to add existing users to their team",
            "Allow Admins to archive users",
            "Maximum revisions",
            "Minimum characters for a revision",
            "Days between revisions"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::sysadmin-panel::instance-settings"
        }
      }
    }
  ]
}
---

# Change server settings

## Trigger

The institution decides that nothing may be public.

## Outcome

People can no longer choose the disallowed levels; the audit log records each change with its old and new value.
