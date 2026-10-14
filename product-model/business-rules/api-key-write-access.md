---
{
  "appliesTo": [
    {
      "type": "context",
      "context": {
        "place": "api"
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/app/controllers/ApiController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controllers/AbstractApiController.php"
    }
  ]
}
---

# A read-only API key never changes anything

Requests made with an API key that may not write can only read; every request acts as the key's holder in the key's team and passes the same permission checks as the web.
