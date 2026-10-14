---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User types a tag name and picks it from the suggestions",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "tag",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    },
    {
      "text": "The Product attaches the tag to the experiment",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "tag",
          "effect": "reads",
          "facts": []
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

# Add an existing tag

## Trigger

The User groups an experiment with others that share a tag.

## Outcome

The experiment lists the tag and appears when the team filters by it.
