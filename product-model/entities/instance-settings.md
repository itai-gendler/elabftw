---
{
  "domain": "sysadmin-panel",
  "singleton": true,
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Config.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/templates/sysconfig.html"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/templates/ts-config.html"
    }
  ]
}
---

# Instance settings

The configuration of the whole instance, kept once and changed by Sysadmins.

## Information kept

- **Timestamping authority** — which Time Stamping Authority trusted timestamps are requested from: DFN, Universign, Digicert, Sectigo, GlobalSign, Evidency or a custom one, among others
- **Monthly timestamp limit** — the most timestamps the instance makes in a sliding month, 0 for no limit
- **Timestamp balance** — how many paid timestamps remain, counted down by each trusted timestamp
- **Blockchain timestamping** — whether blockchain timestamping is offered
- **Allowed visibility levels** — which Visibility and Can write levels people may choose; at least one stays allowed
- **Anonymous visitors** — whether visitors may enter a team anonymously and read what it publishes to everyone
- **Allow Admins to add existing users to their team** — whether team Admins may add people who already have an account
- **Allow Admins to archive users** — whether team Admins may archive members of their team
- **Maximum revisions** — how many revisions are kept per entry, 0 for all
- **Minimum characters for a revision** — how many characters a main text change must add or remove to be kept as a revision
- **Days between revisions** — after how many days without change a new revision is kept regardless of size
- **Local registration** — whether people may register an account themselves
- **Minimum password length** — the fewest characters a password may have
- **Password requirement** — which kinds of characters a password must contain
- **Admin validation** — whether new accounts must be validated before they can sign in
- **Enforce two-factor authentication** — whether two-factor authentication is required of nobody, Sysadmins, Admins or everyone
- **Admins can create local accounts** — whether team Admins may create accounts in their team
- **Allow users to change identity** — whether people may change their own name, email or internal id
- **Restrict compounds editing** — whether only people given the right may change the compounds database
- **Restrict inventory locations editing** — whether only people given the right may change inventory locations
