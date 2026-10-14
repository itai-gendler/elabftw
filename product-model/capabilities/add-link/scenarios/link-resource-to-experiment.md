---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User types the start of a resource's title and picks it",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
          "effect": "reads",
          "facts": [
            "Title"
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
      "text": "The Product links the experiment to the resource",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Linked entries",
            "Last changed by"
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

# Link a resource to an experiment

## Trigger

The User records which antibody an experiment used.

## Outcome

The experiment lists the resource among its links, and the resource lists the experiment among the entries linking to it.

## Edge cases

- Only entries the User can read are offered.
- Import links copies the links of a linked entry into this one.
