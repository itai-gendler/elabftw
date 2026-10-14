---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User deletes an export",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "export-request",
          "effect": "reads",
          "facts": [
            "Format"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::profile"
        }
      }
    },
    {
      "text": "The Product removes the export and its file",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "export-request",
          "effect": "removes",
          "from": "Ready"
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

# Delete an export

## Trigger

The export was downloaded.

## Outcome

The export is no longer listed.
