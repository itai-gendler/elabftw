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

# A password has the minimum length, upper- and lower-case letters, a digit and a special character

A password must have the minimum length, at least one upper-case and one lower-case letter where the alphabet has letter case, a digit and a special character.
