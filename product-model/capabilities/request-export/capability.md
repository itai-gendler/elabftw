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
  "domain": "profile",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Make/Exports.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/import-export.md"
    }
  ]
}
---

# Request an export

Ask the Product to prepare, in the background, an export of one's own experiments, resources or templates, from the Export tab of the profile.
