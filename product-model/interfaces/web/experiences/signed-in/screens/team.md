---
{
  "entities": [
    {
      "entity": "procurement-request",
      "shows": [
        "Quantity ordered",
        "Quantity received",
        "Comment",
        "Quote"
      ],
      "collects": [
        "Quantity received"
      ]
    },
    {
      "entity": "resource",
      "shows": [
        "Title",
        "Price"
      ]
    }
  ],
  "entryPoints": [
    {
      "web": "/team.php"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/team.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/templates/team.html"
    }
  ]
}
---

# Team

The team page where members follow the team's procurement requests.
