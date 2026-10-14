---
{
  "entities": [
    {
      "entity": "status",
      "shows": [
        "Title",
        "Color",
        "Private"
      ],
      "collects": [
        "Title",
        "Color"
      ]
    }
  ],
  "entryPoints": [
    {
      "web": "/resources-status.php"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/resources-status.php"
    }
  ]
}
---

# Resources status

The team's resource statuses, in order, where they are created, edited and deleted.
