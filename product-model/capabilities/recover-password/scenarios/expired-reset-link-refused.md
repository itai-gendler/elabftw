---
{
  "kind": "validation",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Visitor follows a reset link more than 15 minutes old",
      "kind": "actor",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::public::reset-password"
        }
      }
    },
    {
      "text": "The link has expired, so the Product refuses",
      "kind": "condition",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::public::reset-password"
        }
      }
    }
  ]
}
---

# Refuse an expired reset link

## Trigger

The person opened the email too late.

## Outcome

The password is unchanged; a new link can be requested.
