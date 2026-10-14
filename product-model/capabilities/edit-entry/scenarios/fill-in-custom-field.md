---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User fills in a custom field",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    },
    {
      "text": "The Product checks the value against the field's type and saves it",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Custom fields",
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

# Fill in a custom field

## Trigger

The User records a lot number in the field the template provides.

## Outcome

The field shows the value and the changelog records it.

## Edge cases

- A value that does not fit the field's type or choices is refused.
- A field that links to an entry cannot link to the entry itself.
