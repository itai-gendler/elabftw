---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User selects several experiments in the list and chooses the .eln format",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments"
        }
      }
    },
    {
      "text": "The Product packs the experiments the User can read, with their files, into one .eln archive to download",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": [
            "Title",
            "Date",
            "Main text",
            "Custom ID",
            "Category",
            "Status",
            "Tags",
            "Custom fields",
            "eLabID",
            "Owner"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiments"
        }
      }
    }
  ]
}
---

# Export experiments as an .eln archive

## Trigger

The User moves experiments to another ELN.

## Outcome

The browser downloads an RO-Crate .eln archive; entries the User cannot read are left out.
