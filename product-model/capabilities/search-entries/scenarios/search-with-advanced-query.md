---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User writes a query such as status:\"Success\" AND category:\"PCR\"",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "status",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "category",
          "effect": "reads",
          "facts": []
        }
      ],
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
            "Category",
            "Status",
            "Timestamped"
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

# Search with an advanced query

## Trigger

The User needs every successful PCR experiment.

## Outcome

The list shows the readable experiments that match the query.

## Edge cases

- A query the Product cannot parse is reported as an error.
