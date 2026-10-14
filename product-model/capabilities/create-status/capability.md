---
{
  "availability": [
    {
      "place": "web::signed-in"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractStatus.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractCategory.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/experiments-status.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/resources-status.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/templates/admin.html"
    }
  ]
}
---

# Create a status

Add a status to the team's list of experiment or resource statuses. Members may do so unless the team keeps it for its Admins.
