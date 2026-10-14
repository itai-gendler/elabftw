---
{
  "availability": [
    {
      "place": "web::signed-in"
    },
    {
      "place": "api"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Tags.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/TeamTags.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/user-guide/experiments.md"
    }
  ]
}
---

# Add a tag

Attach one of the team's tags to an experiment or resource, creating the tag when it does not exist yet and the team allows it.
