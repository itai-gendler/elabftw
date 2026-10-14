---
{
  "availability": [
    {
      "place": "web::public"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Auth/Local.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Auth/UserLoginValidator.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Auth/LoginFlow.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/login.php"
    }
  ]
}
---

# Sign in

Sign in with an email and a local password. Only validated accounts that have not expired and are not archived in the team get in.
