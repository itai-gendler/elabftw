---
{
  "kind": "primary",
  "routes": {
    "web": "Web"
  },
  "steps": [
    {
      "text": "Someone asked the User to timestamp the experiment",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "action-request",
          "effect": "reads",
          "facts": [
            "Action",
            "Requester"
          ]
        },
        {
          "entity": "experiment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    },
    {
      "text": "The User chooses RFC 3161 timestamping",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    },
    {
      "text": "The Product exports and certifies the experiment and attaches the archive",
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
        },
        {
          "entity": "instance-settings",
          "effect": "reads",
          "facts": [
            "Timestamping authority",
            "Monthly timestamp limit"
          ]
        },
        {
          "entity": "file",
          "effect": "creates",
          "to": "Archived",
          "facts": [
            "Name",
            "Comment",
            "Immutable"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    },
    {
      "text": "The Product marks the experiment timestamped, counts down the timestamp balance, keeps the main text as a revision and marks the User's timestamp request done",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "experiment",
          "effect": "changes",
          "facts": [
            "Timestamped",
            "Timestamped at"
          ]
        },
        {
          "entity": "instance-settings",
          "effect": "changes",
          "facts": [
            "Timestamp balance"
          ]
        },
        {
          "entity": "revision",
          "effect": "creates",
          "facts": [
            "Main text",
            "Saved at"
          ]
        },
        {
          "entity": "action-request",
          "effect": "changes",
          "from": "Pending",
          "to": "Done",
          "facts": []
        }
      ],
      "contexts": {
        "web": {
          "place": "web::signed-in::experiment"
        }
      }
    }
  ]
}
---

# Timestamp an experiment on request

## Trigger

A colleague, often the experiment's owner, asked the User to timestamp it.

## Outcome

The experiment is timestamped and the request no longer shows as pending, even though the User may be unable to change the experiment.
