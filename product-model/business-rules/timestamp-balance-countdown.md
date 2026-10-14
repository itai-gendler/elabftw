---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "instance-settings",
      "effect": "changes",
      "facts": [
        "Timestamp balance"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "user"
      ]
    },
    {
      "actors": [
        "sysadmin"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Config.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractEntity.php"
    }
  ]
}
---

# Whoever makes a trusted timestamp counts down the timestamp balance

Each trusted timestamp, by any person allowed to make it, takes one from the instance's timestamp balance while it is above zero; Sysadmins see the balance on the Timestamp tab.
