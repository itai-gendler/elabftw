---
{
  "type": "web",
  "actors": [
    "visitor",
    "user",
    "sysadmin"
  ],
  "entryPoints": [
    {
      "web": "/login.php"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/index.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/login.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controllers/AbstractEntityController.php"
    }
  ]
}
---

# Web

The browser application people use to keep their lab notebook: sign in or register, record experiments and resources, administer a team and, for Sysadmins, the whole instance.
