---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User, an Admin, switches the settings that govern what members may create",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::admin-panel"
        }
      }
    },
    {
      "text": "The Product saves the team's settings",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "changes",
          "facts": [
            "Allow users to create experiments",
            "Allow users to create resources",
            "Allow users to create experiments templates",
            "Allow users to create resources templates",
            "Allow users to create and edit experiment status",
            "Allow users to create and edit resources status",
            "Force experiment template use",
            "Force resource template use",
            "Announcement",
            "Allow users to create and edit experiments categories",
            "Allow users to create and edit resources categories",
            "Capture reason for container deletion"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::admin-panel"
        }
      }
    }
  ]
}
---

# Change team settings

## Trigger

The Admin wants every experiment to start from an approved template.

## Outcome

Members are held to the new settings from their next action; Admins are not.
