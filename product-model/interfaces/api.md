---
{
  "type": "api",
  "actors": [
    "user"
  ],
  "entryPoints": [
    {
      "api": "/api/v2/"
    }
  ],
  "references": [
    {
      "kind": "doc",
      "role": "intent",
      "target": "apidoc/v2/openapi.yaml"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controllers/Apiv2Controller.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/app/controllers/ApiController.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/api.md"
    }
  ]
}
---

# REST API

The public REST API (version 2) that people's own scripts and integrations use with an API key, acting as the key's holder in the key's team. A key that is not allowed to write can only read.
