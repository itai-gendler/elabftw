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
      "target": "src/Import/Handler.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Import/Eln.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Import/Csv.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/import-export.md"
    }
  ]
}
---

# Import a file

Create experiments, resources or templates from an .eln archive or a CSV file, from the Import tab of the profile. Admins can import on behalf of a member of their team.
