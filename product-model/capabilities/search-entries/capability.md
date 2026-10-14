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
      "target": "src/Models/AbstractEntity.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/AdvancedSearchQuery.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/user-guide/misc.md"
    }
  ]
}
---

# Search entries

Find experiments or resources the person can read, by words in their title, text or custom ID, by an advanced query on fields such as author, status, category, date, custom fields or timestamp, and by state.
