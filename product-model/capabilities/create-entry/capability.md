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
      "target": "src/Models/Experiments.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Items.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractConcreteEntity.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/templates/create-new-modal.html"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/ts/common.ts"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/user-guide/experiments.md"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/user-guide/templates.md"
    }
  ]
}
---

# Create an entry

Create a new experiment or resource in the team the person is signed in to, blank or from a template. A blank entry takes the person's default permissions; one created from a template copies the template's content and the permissions it sets for new entries. The new entry opens in edit mode.
