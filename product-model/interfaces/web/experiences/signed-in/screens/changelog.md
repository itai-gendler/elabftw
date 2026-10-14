---
{
  "entities": [
    {
      "entity": "changelog-entry",
      "shows": [
        "Who",
        "What changed",
        "New value",
        "When"
      ]
    },
    {
      "entity": "experiment",
      "shows": [
        "Title"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/templates/changelog.html"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controllers/AbstractEntityController.php"
    }
  ]
}
---

# Changelog

Every recorded change to one entry, newest first.
