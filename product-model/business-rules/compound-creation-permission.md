---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "compound",
      "effect": "creates"
    }
  ],
  "permits": [
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "entity": "instance-settings",
          "fact": "Restrict compounds editing",
          "is": "Off"
        }
      ]
    },
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "entity": "user",
          "fact": "Can manage compounds",
          "is": "Yes"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Compounds.php"
    }
  ]
}
---

# Anyone signed in adds compounds unless the instance restricts it to people given the right

The compounds database is shared by the whole instance. With “Restrict compounds editing” on, only people a Sysadmin gave the right may change it.
