---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User removes a container from the resource",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "container",
          "effect": "reads",
          "facts": [
            "Quantity",
            "Unit"
          ]
        },
        {
          "entity": "resource",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::resource"
        }
      }
    },
    {
      "text": "The Product removes the container and records the removal in the resource's changelog",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "container",
          "effect": "removes"
        },
        {
          "entity": "resource",
          "effect": "changes",
          "facts": [
            "Last changed by"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::resource"
        }
      }
    }
  ]
}
---

# Remove a container

## Trigger

The bottle is used up.

## Outcome

The container is no longer listed.

## Decision points

### Is a reason asked for?

Does the resource's team capture a reason for container deletion?

- It does → the User picks a reason, which the changelog records
- It does not → no reason is asked
