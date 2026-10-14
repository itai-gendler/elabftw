---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User selects a CSV file and chooses Resources, a category and a template",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "resource",
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
          "place": "web::signed-in::profile"
        }
      }
    },
    {
      "text": "The Product creates one resource per row from the template, with the title, custom fields and location the row gives",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "resource-template",
          "effect": "reads",
          "facts": [
            "Title",
            "Main text",
            "Category",
            "Status",
            "Tags",
            "Custom fields",
            "Entry visibility",
            "Entry write permission",
            "Lock down read permissions",
            "Lock down write permissions"
          ]
        },
        {
          "entity": "resource",
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
            "Team",
            "Created from"
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

# Import resources from CSV

## Trigger

The lab moves its antibody spreadsheet into eLabFTW.

## Outcome

Each row is a resource; unknown columns become custom fields.

## Edge cases

- A row without a title is reported as an error.
