---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
        "Last login"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "visitor"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Auth/LoginHelper.php"
    }
  ]
}
---

# Signing in records the login on the account

The account keeps when its holder last signed in, written by the sign-in itself.
