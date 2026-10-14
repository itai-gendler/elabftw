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

# A password has the minimum length and upper- and lower-case letters

A password must have the minimum length and at least one upper-case and one lower-case letter, where the alphabet has letter case.
