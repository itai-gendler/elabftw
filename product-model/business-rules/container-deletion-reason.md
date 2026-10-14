---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "remove-container",
      "contexts": [
        {
          "place": "web::signed-in::resource"
        },
        {
          "place": "web::signed-in::experiment"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Links/AbstractContainersLinks.php"
    }
  ]
}
---

# Where the team captures it, removing a container records a reason

With “Capture reason for container deletion” on for the entry's team, a container is removed only with a reason, which the changelog keeps.
