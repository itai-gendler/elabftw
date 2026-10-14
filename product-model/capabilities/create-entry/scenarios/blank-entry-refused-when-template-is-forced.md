---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Create without picking a template",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments"
        }
      }
    },
    {
      "text": "The team forces template use, so the Product refuses the blank entry",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": [
            "Force experiment template use"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments"
        }
      }
    }
  ]
}
---

# Refuse a blank entry when the team forces templates

## Trigger

The User tries to start a blank experiment in a team that requires templates.

## Outcome

No experiment is created; the User is told the team administrator has disabled creating entries without a template.
