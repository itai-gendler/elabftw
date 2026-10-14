---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User, an Admin, deletes a tag",
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
          "place": "web::signed-in::admin-panel"
        }
      }
    },
    {
      "text": "The Product deletes the tag and detaches it from every entry",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "tag",
          "effect": "removes"
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

# Delete a tag

## Trigger

A tag is obsolete.

## Outcome

No entry carries the tag any more.
