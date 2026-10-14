---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The User, an Admin, archives a member",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "team-membership",
          "effect": "reads",
          "facts": [
            "Role"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::admin-panel"
        }
      }
    },
    {
      "text": "The account has not been validated, so the Product refuses and suggests deleting it instead",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Validated"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::admin-panel"
        }
      }
    }
  ]
}
---

# Refuse to archive an unvalidated member

## Trigger

An Admin tries to archive someone who never got access.

## Outcome

The membership stays active.
