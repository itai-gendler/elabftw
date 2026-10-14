---
{
  "entities": [
    {
      "entity": "resource",
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
        "Bookable",
        "Linked entries",
        "Compounds",
        "Share link",
        "Overlapping slots allowed",
        "Maximum time per slot",
        "Maximum future bookings per user",
        "Booking window",
        "Booking in the past allowed",
        "Cancellable",
        "Minimum cancellation notice",
        "Procurable",
        "Pack quantity",
        "Price"
      ],
      "collects": [
        "Title",
        "Date",
        "Main text",
        "Custom fields",
        "Bookable",
        "Overlapping slots allowed",
        "Maximum time per slot",
        "Maximum future bookings per user",
        "Booking window",
        "Booking in the past allowed",
        "Cancellable",
        "Minimum cancellation notice",
        "Procurable",
        "Pack quantity",
        "Price"
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
      "entity": "experiment",
      "shows": [
        "Title"
      ]
    },
    {
      "entity": "procurement-request",
      "collects": [
        "Quantity ordered",
        "Comment",
        "Quote"
      ]
    }
  ],
  "entryPoints": [
    {
      "web": "/database.php?mode=view&id=<id>"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/database.php"
    }
  ]
}
---

# Resource

One resource, in view or edit mode, with the same sections and toolbar as an experiment.
