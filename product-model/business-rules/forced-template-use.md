---
{
  "appliesTo": [
    {
      "type": "capability-scenario",
      "id": "create-blank-experiment"
    },
    {
      "type": "capability-scenario",
      "id": "blank-entry-refused-when-template-is-forced"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractConcreteEntity.php"
    }
  ]
}
---

# Where the team forces template use, entries are only created from a template

With “Force experiment template use” or “Force resource template use” on, a blank entry of that kind is refused for everyone in the team, Admins included; creating from a template is unaffected.
