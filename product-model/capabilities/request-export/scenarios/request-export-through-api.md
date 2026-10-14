---
{
  "kind": "primary",
  "routes": {
    "api": "API"
  },
  "steps": [
    {
      "text": "The User sends an export request with a format",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "export-request",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "api": {
          "place": "api"
        }
      }
    },
    {
      "text": "The Product records the pending export",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "export-request",
          "effect": "creates",
          "to": "Pending",
          "facts": [
            "Format",
            "Content"
          ]
        }
      ],
      "contexts": {
        "api": {
          "place": "api"
        }
      }
    }
  ]
}
---

# Request an export through the API

## Trigger

A backup script requests archives.

## Outcome

The API answers 201 Created with the export's address.
