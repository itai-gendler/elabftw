---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User selects a file that is neither .eln nor .csv",
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
      "text": "The Product refuses and lists the allowed extensions",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::profile"
        }
      }
    }
  ]
}
---

# Refuse an unsupported file

## Trigger

Someone tries to import a spreadsheet in another format.

## Outcome

Nothing is imported.
