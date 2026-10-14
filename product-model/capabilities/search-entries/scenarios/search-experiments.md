---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User types words in the search bar",
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
      "text": "The User reads the matching experiments",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": [
            "Title",
            "Date",
            "Custom ID",
            "Category",
            "Status",
            "Tags",
            "Owner"
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

# Search experiments

## Trigger

The User looks for an experiment they remember part of.

## Outcome

The list shows the experiments the User can read that match, most recently changed first.

## Edge cases

- A number also matches an entry with that id or Custom ID.
