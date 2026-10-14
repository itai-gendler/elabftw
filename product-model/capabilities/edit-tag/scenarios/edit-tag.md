---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User, an Admin, renames a tag in the tag manager",
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
      "text": "The Product renames the tag everywhere it is attached",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "tag",
          "effect": "changes",
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
    }
  ]
}
---

# Edit a tag

## Trigger

The team has “RPE1” and wants it written “RPE-1”.

## Outcome

Every entry carrying the tag shows the new name.
