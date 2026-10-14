---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User sets the permissions new entries get",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::resource-template"
        }
      }
    },
    {
      "text": "The Product saves them on the template",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "resource-template",
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
          "place": "web::signed-in::resource-template"
        }
      }
    }
  ]
}
---

# Set a resource template's entry permissions

## Trigger

The team lets members edit resources made from a template it alone maintains.

## Outcome

Resources created from the template from now on start with these permissions.
