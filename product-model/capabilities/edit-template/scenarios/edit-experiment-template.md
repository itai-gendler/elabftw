---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User changes the template's title, text or fields",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment-template"
        }
      }
    },
    {
      "text": "The Product saves them on the template",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment-template",
          "effect": "changes",
          "facts": [
            "Title",
            "Main text",
            "Custom fields"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment-template"
        }
      }
    }
  ]
}
---

# Edit an experiment template

## Trigger

The team improves its PCR procedure.

## Outcome

Experiments created from the template from now on start with the new content.
