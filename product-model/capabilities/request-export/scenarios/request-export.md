---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User picks a format and what to include and requests the export",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::profile"
        }
      }
    },
    {
      "text": "The Product records the pending export and starts preparing it",
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
        "web": {
          "place": "web::signed-in::profile"
        }
      }
    }
  ]
}
---

# Request an export

## Trigger

The User wants a full archive of their notebook.

## Outcome

The export is listed as pending on the profile.
