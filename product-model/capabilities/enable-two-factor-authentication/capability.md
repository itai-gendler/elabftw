---
{
  "availability": [
    {
      "place": "web::signed-in"
    }
  ],
  "domain": "settings",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/app/controllers/UcpController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/MfaHelper.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/user-guide/settings.md"
    }
  ]
}
---

# Enable two-factor authentication

Turn on two-factor authentication for one's own account by scanning a QR code with an authenticator app and entering its code.
