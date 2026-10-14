---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "sign-in",
      "contexts": [
        {
          "place": "web::public::login"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Auth/UserLoginValidator.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Auth/LoginFlow.php"
    }
  ]
}
---

# Only a validated, unexpired account that is not archived in the team signs in

An account awaiting validation, past its Valid until date, or archived in the team, or in all its teams, is refused at sign-in.
