---
{
  "entities": [
    {
      "entity": "storage-unit",
      "shows": [
        "Name",
        "Parent",
        "Capacity"
      ],
      "collects": [
        "Name",
        "Capacity"
      ]
    },
    {
      "entity": "container",
      "shows": [
        "Quantity",
        "Unit"
      ]
    }
  ],
  "entryPoints": [
    {
      "web": "/inventory.php"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/inventory.php"
    }
  ]
}
---

# Inventory

The tree of storage locations and the containers stored in them.
