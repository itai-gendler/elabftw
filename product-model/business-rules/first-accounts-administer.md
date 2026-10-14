---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-account",
      "contexts": [
        {
          "place": "web::public::register"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/TeamsHelper.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Users/Users.php"
    }
  ]
}
---

# The first account of an instance is a Sysadmin, and the first member of a team is its Admin

Both are validated at once, whatever the Admin validation setting; everyone else joins as a User and waits for validation while Admin validation is on.
