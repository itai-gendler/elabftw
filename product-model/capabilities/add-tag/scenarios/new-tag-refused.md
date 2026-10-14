---
{
  "kind": "validation",
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
      "text": "The team keeps creating tags for its Admins and the User is not one, so the Product refuses",
      "kind": "condition",
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
          "effect": "reads",
          "facts": []
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

# Refuse a new tag

## Trigger

A member tries to invent a tag in a team that restricts them.

## Outcome

No tag is created; the User is told users cannot create tags.
