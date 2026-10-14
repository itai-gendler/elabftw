---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "storage-unit",
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
          "fact": "Restrict inventory locations editing",
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
          "fact": "Can manage inventory locations",
          "is": "Yes"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/StorageUnits.php"
    }
  ]
}
---

# Anyone signed in adds storage locations unless the instance restricts it to people given the right

Inventory locations are shared. With “Restrict inventory locations editing” on, only people a Sysadmin gave the right may change them.
