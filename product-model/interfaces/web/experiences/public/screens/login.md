---
{
  "entities": [
    {
      "entity": "account",
      "collects": [
        "Email",
        "Password"
      ]
    }
  ],
  "entryPoints": [
    {
      "web": "/login.php"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/login.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Auth/Local.php"
    }
  ]
}
---

# Sign-in page

Where a person enters their email and password to sign in.
