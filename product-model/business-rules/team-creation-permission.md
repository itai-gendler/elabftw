---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "team",
      "effect": "creates"
    }
  ],
  "permits": [
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
      "target": "src/Models/Teams.php"
    }
  ]
}
---

# Only a Sysadmin creates a team

Teams are added from the Sysadmin panel; each starts with the default experiment statuses.
