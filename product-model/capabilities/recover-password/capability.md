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
      "target": "web/app/controllers/ResetPasswordController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/ResetPasswordKey.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/change-pass.php"
    }
  ]
}
---

# Recover a password

Get a password reset link by email from the sign-in page and choose a new password through it. The link works for 15 minutes.
