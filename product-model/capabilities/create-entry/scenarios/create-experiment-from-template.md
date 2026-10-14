---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User chooses Create and starts from a template",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment-template",
          "effect": "reads",
          "facts": [
            "Title"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments"
        }
      }
    },
    {
      "text": "The Product creates a Normal experiment from the template, copying its content, steps, attached files and the permissions it sets for new entries",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment-template",
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
            "Team",
            "Created from"
          ]
        },
        {
          "entity": "step",
          "effect": "creates",
          "to": "Unfinished",
          "facts": [
            "Text",
            "Deadline",
            "Locked"
          ],
          "with": "experiment"
        },
        {
          "entity": "file",
          "effect": "creates",
          "to": "Normal",
          "facts": [
            "Name",
            "Comment",
            "Immutable"
          ],
          "with": "experiment"
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

# Create an experiment from a template

## Trigger

The User records a repeated procedure their team keeps as a template.

## Outcome

A new Normal experiment carries the template's text, custom fields with their defaults, steps, tags, category and status, starts with the template's entry permissions, locked down where the template says so, and records which template it came from.

## Edge cases

- Steps the template locks arrive locked.
- Custom fields marked to be blanked on duplicate keep their template defaults here.
