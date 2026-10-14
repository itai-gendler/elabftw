---
{
  "kind": "edge",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "An export is pending",
      "kind": "condition",
      "unattended": true,
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
      "text": "The Product cannot write the file and marks the request as failed with the reason",
      "kind": "product",
      "entities": [
        {
          "entity": "export-request",
          "effect": "changes",
          "from": "Pending",
          "to": "Error",
          "facts": []
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

# Report a failed export

## Trigger

Preparing a requested export fails.

## Outcome

The profile shows the export in error with its reason.
