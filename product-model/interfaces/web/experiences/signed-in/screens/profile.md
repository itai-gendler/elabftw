---
{
  "entities": [
    {
      "entity": "export-request",
      "shows": [
        "Format",
        "Content",
        "File"
      ],
      "collects": [
        "Format",
        "Content"
      ]
    },
    {
      "entity": "resource",
      "shows": [
        "Title"
      ]
    },
    {
      "entity": "category",
      "shows": [
        "Title"
      ]
    },
    {
      "entity": "team",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "file",
      "shows": [
        "Name"
      ]
    }
  ],
  "entryPoints": [
    {
      "web": "/profile.php"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/profile.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/templates/profile.html"
    }
  ]
}
---

# Profile

The person's profile, with the tabs to import files and to prepare and download exports.
