---
{
  "entities": [
    {
      "entity": "to-do-item",
      "shows": [
        "Text",
        "Order"
      ],
      "collects": [
        "Text"
      ]
    },
    {
      "entity": "step",
      "shows": [
        "Text",
        "Deadline"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/templates/todolist-panel.html"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Todolist.php"
    }
  ]
}
---

# To-do list

The person's own to-do list and their unfinished steps, opened from any page.
