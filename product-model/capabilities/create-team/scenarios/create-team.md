---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Sysadmin enters a team name",
      "kind": "actor",
      "actor": "sysadmin",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::sysadmin-panel::instance-settings"
        }
      }
    },
    {
      "text": "The Product creates the team with its default statuses",
      "kind": "product",
      "actor": "sysadmin",
      "entities": [
        {
          "entity": "team",
          "effect": "creates",
          "facts": [
            "Name"
          ]
        },
        {
          "entity": "status",
          "effect": "creates",
          "to": "Normal",
          "facts": [
            "Title",
            "Color",
            "Private",
            "Applies to"
          ],
          "with": "team"
        }
      ],
      "contexts": {
        "web": {
          "place": "web::sysadmin-panel::instance-settings"
        }
      }
    }
  ]
}
---

# Create a team

## Trigger

A new research group joins the institute.

## Outcome

The team can be chosen at registration and its first member becomes its Admin.
