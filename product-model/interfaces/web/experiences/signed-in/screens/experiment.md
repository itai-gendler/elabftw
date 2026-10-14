---
{
  "entities": [
    {
      "entity": "experiment",
      "shows": [
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
        "Locked",
        "Locked by",
        "Timestamped",
        "Timestamped at",
        "Signature count",
        "Last signed at",
        "eLabID",
        "Created from",
        "Owner",
        "Last changed by",
        "Linked entries",
        "Compounds",
        "Share link"
      ],
      "collects": [
        "Title",
        "Date",
        "Main text",
        "Custom fields"
      ]
    },
    {
      "entity": "status",
      "shows": [
        "Title",
        "Color"
      ]
    },
    {
      "entity": "category",
      "shows": [
        "Title",
        "Color",
        "Text color"
      ]
    },
    {
      "entity": "tag",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "step",
      "shows": [
        "Text",
        "Deadline",
        "Locked",
        "Finished at"
      ],
      "collects": [
        "Text"
      ]
    },
    {
      "entity": "comment",
      "shows": [
        "Text"
      ],
      "collects": [
        "Text"
      ]
    },
    {
      "entity": "file",
      "shows": [
        "Name",
        "Comment"
      ],
      "collects": [
        "Name",
        "Comment"
      ]
    },
    {
      "entity": "action-request",
      "shows": [
        "Action",
        "Requester",
        "Target user"
      ]
    },
    {
      "entity": "container",
      "shows": [
        "Quantity",
        "Unit"
      ],
      "collects": [
        "Quantity",
        "Unit"
      ]
    },
    {
      "entity": "storage-unit",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "compound",
      "shows": [
        "Name",
        "CAS number"
      ]
    },
    {
      "entity": "resource",
      "shows": [
        "Title"
      ]
    }
  ],
  "entryPoints": [
    {
      "web": "/experiments.php?mode=view&id=<id>"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/experiments.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/templates/view-edit-toolbar.html"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controllers/AbstractEntityController.php"
    }
  ]
}
---

# Experiment

One experiment, in view or edit mode: its text, fields, steps, links, attached files, comments, permissions and the toolbar actions.
