---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "creates",
      "facts": [
        "Password"
      ]
    },
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
        "Password"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Enums/PasswordComplexity.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/PasswordValidator.php"
    }
  ]
}
---

# A password has at least the minimum length

With the “Minimum password length” requirement, a password set at registration, on change or on reset only needs the instance's minimum number of characters, 12 by default.
