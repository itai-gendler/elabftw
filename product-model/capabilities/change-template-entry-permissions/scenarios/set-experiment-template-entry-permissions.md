---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User sets the permissions new entries get and locks down their visibility",
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
            "Entry visibility",
            "Entry write permission",
            "Lock down read permissions",
            "Lock down write permissions"
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

# Set an experiment template's entry permissions

## Trigger

The team wants every experiment from a template visible to the team and unchangeable in that respect.

## Outcome

Experiments created from the template from now on start with these permissions; existing ones are unchanged.
