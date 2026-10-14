---
{
  "kind": "primary",
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
            "Format",
            "Content"
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
      "text": "The Product prepares the export file and marks the request ready",
      "kind": "product",
      "entities": [
        {
          "entity": "export-request",
          "effect": "changes",
          "from": "Pending",
          "to": "Ready",
          "facts": [
            "File"
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

# Prepare an export

## Trigger

The Product picks up a pending export.

## Outcome

The export is ready to download from the profile.
