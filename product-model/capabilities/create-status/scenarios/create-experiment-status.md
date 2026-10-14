---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User enters a name and a color",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments-status"
        }
      }
    },
    {
      "text": "The team lets members manage this list, or the User is an Admin",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": [
            "Allow users to create and edit experiment status"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments-status"
        }
      }
    },
    {
      "text": "The Product adds the new private status to the team's list",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": []
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
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments-status"
        }
      }
    }
  ]
}
---

# Create an experiment status

## Trigger

The team needs a status such as “Waiting for reagents”.

## Outcome

The status is offered on the team's experiments.
