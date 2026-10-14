---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User types a tag name nobody has used yet",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "tag",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    },
    {
      "text": "The Product creates the tag in the team and attaches it to the experiment",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": [
            "Allow users to create new tags"
          ]
        },
        {
          "entity": "tag",
          "effect": "creates",
          "facts": [
            "Name"
          ]
        },
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Tags"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    }
  ]
}
---

# Add a new tag

## Trigger

The User needs a label the team does not have.

## Outcome

The new tag exists for the whole team and is attached to the experiment.
