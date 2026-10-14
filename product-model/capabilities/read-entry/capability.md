---
{
  "availability": [
    {
      "place": "web::signed-in"
    },
    {
      "place": "web::public"
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
      "target": "src/Elabftw/Permissions.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controllers/AbstractEntityController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Users/AnonymousUser.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/user-guide/experiments.md"
    }
  ]
}
---

# Read an entry

Open an experiment or resource to read it. Who may read it follows its Visibility; an entry someone cannot change opens read-only, and so does a locked or deleted one.
