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
          "place": "web::signed-in::resources-status"
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
            "Allow users to create and edit resources status"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::resources-status"
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
          "place": "web::signed-in::resources-status"
        }
      }
    }
  ]
}
---

# Create a resource status

## Trigger

The team tracks stock with statuses such as “Low”.

## Outcome

The status is offered on the team's resources.
