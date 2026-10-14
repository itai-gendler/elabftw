---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User, an Admin, selects a file and a member of the team as owner",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::profile"
        }
      }
    },
    {
      "text": "The chosen owner belongs to the team",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "team",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::profile"
        }
      }
    },
    {
      "text": "The Product creates the entries owned by that member",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "creates",
          "to": "Normal",
          "facts": [
            "Title",
            "Date",
            "Main text",
            "Custom ID",
            "Category",
            "Status",
            "Tags",
            "Custom fields",
            "Visibility",
            "Can write",
            "Visibility locked down",
            "Can write locked down",
            "Locked",
            "Timestamped",
            "Signature count",
            "eLabID",
            "Owner",
            "Team"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::profile"
        }
      }
    }
  ]
}
---

# Import on behalf of a member

## Trigger

An Admin migrates a member's data.

## Outcome

The entries belong to the member.
