---
{
  "domain": "admin-panel",
  "relations": [
    {
      "entity": "team-membership",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "experiment",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "resource",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "experiment-template",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "resource-template",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "status",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "category",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "tag",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "event",
      "verb": "holds",
      "cardinality": "one-to-many"
    },
    {
      "entity": "user-group",
      "verb": "keeps",
      "cardinality": "one-to-many"
    },
    {
      "entity": "procurement-request",
      "verb": "holds",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Teams.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/sql/structure.sql"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/templates/admin.html"
    }
  ]
}
---

# Team

A research group hosted on the instance. Experiments, resources, templates, statuses, categories and tags belong to a team, and its Admins decide what its members may create.

## Information kept

- **Name** — the team name
- **Allow users to create experiments** — whether members who are not Admins may create experiments
- **Allow users to create resources** — whether members who are not Admins may create resources
- **Allow users to create experiments templates** — whether members who are not Admins may create experiment templates
- **Allow users to create resources templates** — whether members who are not Admins may create resource templates
- **Allow users to create and edit experiment status** — whether members who are not Admins may create, edit and delete experiment statuses; on by default
- **Allow users to create and edit resources status** — whether members who are not Admins may create, edit and delete resource statuses; on by default
- **Force experiment template use** — whether experiments may only be created from a template
- **Force resource template use** — whether resources may only be created from a template
- **Allow users to create new tags** — whether members who are not Admins may create tags that do not exist yet
- **Announcement** — a message shown to members on every page while it is set
- **Capture reason for container deletion** — whether removing a container from an entry of the team asks for a reason, recorded in its changelog
- **Allow users to create and edit experiments categories** — whether members who are not Admins may create, edit and delete experiment categories; on by default
- **Allow users to create and edit resources categories** — whether members who are not Admins may create, edit and delete resource categories; on by default
