---
{
  "domain": "settings",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Users/Users.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/sql/structure.sql"
    }
  ]
}
---

# Account

The person behind a User or Sysadmin: identity, sign-in credentials and personal defaults that hold whatever teams or role they have.

## Information kept

- **Name** — first and last name
- **Email** — the address used to sign in and receive notifications, unique on the instance
- **Password** — the local password, checked against the instance password requirement whenever it is set
- **Validated** — whether an Admin, a Sysadmin or the registration rules have validated the account; an unvalidated account cannot sign in
- **Valid until** — an optional expiry date after which the account cannot sign in
- **Last login** — when the person last signed in
- **Preferred language** — the language the interface is shown in
- **Default visibility** — the Visibility given to entries the person creates without a template
- **Default write permission** — the Can write setting given to entries the person creates without a template
- **Markdown editor** — whether new entries are written in Markdown instead of the rich text editor
- **ORCID** — the person's ORCID identifier
- **Two-factor authentication** — whether signing in also asks for a code from an authenticator app
- **Pinned entries** — the entries the person pinned to the top of their lists
- **Notification preferences** — which events notify the person in the Product and by email
