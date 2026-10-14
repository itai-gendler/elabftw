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
      "target": "src/Controllers/MakeController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Make/MakePdf.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Make/MakeEln.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/import-export.md"
    }
  ]
}
---

# Export an entry

Download one or several readable experiments or resources as PDF, PDF/A, ZIP, .eln, CSV, JSON or QR code. Exporting many entries at once is recorded in the audit log.
