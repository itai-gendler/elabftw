---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "The Visitor chooses Forgot password and enters their email",
      "kind": "actor",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::public::login"
        }
      }
    },
    {
      "text": "The Product emails a reset link to the account and shows the same message whether or not an account exists",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Email"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::public::login"
        }
      }
    },
    {
      "text": "The Visitor follows the link and enters a new password",
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
      "text": "The new password meets the instance requirement",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Minimum password length",
            "Password requirement"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::public::reset-password"
        }
      }
    },
    {
      "text": "The Product sets the new password and returns the Visitor to the sign-in page",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Password"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::public::reset-password"
        }
      }
    }
  ]
}
---

# Reset a password by email

## Trigger

A person forgot their password.

## Outcome

The person signs in with the new password; the audit log records the request.
