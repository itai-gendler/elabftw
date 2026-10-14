---
{
  "entities": [
    {
      "entity": "account",
      "shows": [
        "Name",
        "Email",
        "Preferred language",
        "Default visibility",
        "Default write permission",
        "Markdown editor",
        "ORCID",
        "Two-factor authentication",
        "Notification preferences"
      ],
      "collects": [
        "Password",
        "Preferred language",
        "Default visibility",
        "Default write permission",
        "Markdown editor",
        "Name",
        "Email",
        "ORCID",
        "Two-factor authentication",
        "Notification preferences"
      ]
    },
    {
      "entity": "signature-key",
      "shows": [
        "Public key",
        "Last used at"
      ]
    },
    {
      "entity": "api-key",
      "shows": [
        "Name",
        "Can write",
        "Team",
        "Last used at"
      ],
      "collects": [
        "Name",
        "Can write"
      ]
    }
  ],
  "entryPoints": [
    {
      "web": "/ucp.php"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/ucp.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/templates/ucp.html"
    }
  ]
}
---

# Settings

The person's own settings: general preferences and default permissions, account and password, signature keys and API keys.
