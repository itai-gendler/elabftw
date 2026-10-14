---
{
  "entities": [
    {
      "entity": "team",
      "shows": [
        "Name",
        "Allow users to create experiments",
        "Allow users to create resources",
        "Allow users to create experiments templates",
        "Allow users to create resources templates",
        "Allow users to create and edit experiment status",
        "Allow users to create and edit resources status",
        "Force experiment template use",
        "Force resource template use",
        "Allow users to create new tags",
        "Announcement",
        "Allow users to create and edit experiments categories",
        "Allow users to create and edit resources categories",
        "Capture reason for container deletion"
      ]
    },
    {
      "entity": "team-membership",
      "shows": [
        "Role"
      ]
    },
    {
      "entity": "account",
      "shows": [
        "Name",
        "Email",
        "Validated",
        "Valid until",
        "Last login"
      ],
      "collects": [
        "Name",
        "Email",
        "Valid until"
      ]
    },
    {
      "entity": "tag",
      "shows": [
        "Name"
      ],
      "collects": [
        "Name"
      ]
    },
    {
      "entity": "user-group",
      "shows": [
        "Name",
        "Members"
      ],
      "collects": [
        "Name",
        "Members"
      ]
    },
    {
      "entity": "category",
      "shows": [
        "Title"
      ]
    }
  ],
  "entryPoints": [
    {
      "web": "/admin.php"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/admin.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/templates/admin.html"
    }
  ]
}
---

# Admin panel

The administration of the team the person is signed in to, open to its Admins: team settings, members, accounts awaiting validation and the tag manager.
