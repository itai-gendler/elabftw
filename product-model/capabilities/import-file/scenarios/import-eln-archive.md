---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User selects an .eln archive and the permissions the entries get",
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
      "text": "The Product creates an entry for each item in the archive, of the kind its genre gives, with its files, steps and changelog",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "creates",
          "to": "Normal",
          "facts": [
            "Title",
            "Date",
            "Main text",
            "Custom ID",
            "Category",
            "Status",
            "Tags",
            "Custom fields",
            "Visibility",
            "Can write",
            "Visibility locked down",
            "Can write locked down",
            "Locked",
            "Timestamped",
            "Signature count",
            "eLabID",
            "Owner",
            "Team"
          ]
        },
        {
          "entity": "step",
          "effect": "creates",
          "to": "Unfinished",
          "facts": [
            "Text",
            "Deadline",
            "Locked"
          ],
          "with": "experiment"
        },
        {
          "entity": "file",
          "effect": "creates",
          "to": "Normal",
          "facts": [
            "Name",
            "Comment",
            "Immutable"
          ],
          "with": "experiment"
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

# Import an .eln archive

## Trigger

A group moves its notebook from another eLabFTW instance.

## Outcome

The imported entries belong to the User in their current team; the audit log records the import.

## Edge cases

- The User can force every entry to one kind and category.
