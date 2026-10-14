---
{
  "relations": [
    {
      "entity": "comment",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "step",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "file",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "revision",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "action-request",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "event",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "procurement-request",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "container",
      "verb": "has",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Items.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/AbstractEntity.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/user-guide/resources.md"
    }
  ]
}
---

# Resource

An entry in the team's database of things used in experiments, such as antibodies, plasmids, cell lines, chemicals or equipment, which can also be made bookable.

## Information kept

- **Title** — the name shown before the entry in lists and on its page, “Untitled” when left empty
- **Date** — the day the work started, today by default and editable; the creation time is kept apart and never changes
- **Main text** — the free-form body, written in the rich text editor or in Markdown
- **Custom ID** — an optional number unique within the entry's category, shown before the title
- **Category** — the team category the entry belongs to, if any
- **Status** — the team status the entry currently shows, if any
- **Tags** — the team tags attached to the entry
- **Custom fields** — structured extra fields and their values
- **Visibility** — who may read it: Everyone including anonymous users, Everyone with an account, Only members of the team, Only owner and admins, or Only owner, widened by any teams, user groups and users added to it
- **Can write** — who may change it, on the same levels and with the same kind of additions as Visibility
- **Visibility locked down** — whether only Admins may change its Visibility, inherited from the template it was created from
- **Can write locked down** — whether only Admins may change its Can write setting, inherited from the template it was created from
- **Locked** — whether it is locked against further editing
- **Locked by** — who locked it, and when
- **Timestamped** — whether a timestamp archive has been made for it
- **Timestamped at** — the time of its latest timestamp
- **Signature count** — how many cryptographic signatures it has received
- **Last signed at** — when, and by whom, it was last signed
- **eLabID** — a unique identifier generated at creation that never changes, for referencing it from other systems
- **Created from** — the template or entry it was created from, if any
- **Owner** — the person who owns it
- **Team** — the team it belongs to
- **Last changed by** — who last changed its content, steps, links or files, and when
- **Bookable** — whether it can be booked in the scheduler
- **Booking permission** — who may book it, on the same levels as Visibility
- **Linked entries** — the experiments and resources it links to
- **Compounds** — the compounds from the instance database it refers to
- **Share link** — an optional secret link that lets anyone holding it read the entry
- **Overlapping slots allowed** — whether bookings of it may overlap
- **Maximum time per slot** — the longest a single booking may last, in minutes, 0 for no limit
- **Maximum future bookings per user** — how many upcoming bookings one person may hold, 0 for no limit
- **Booking window** — how many days ahead it may be booked, 0 for no limit
- **Booking in the past allowed** — whether people who are not Admins may book it in the past
- **Cancellable** — whether people who are not Admins may cancel a booking of it
- **Minimum cancellation notice** — how many minutes before its start a booking can still be cancelled by people who are not Admins
- **Procurable** — whether it can be ordered through procurement requests
- **Pack quantity** — how many units one order brings
- **Price** — the price of one pack, with and without taxes, in the chosen currency

## States

### Normal

Listed by default, and readable and changeable within its permissions.

### Archived

Left out of default lists and exports and locked; the only change it accepts is being unarchived.

### Deleted

In the trash: left out of lists, searches and exports, kept read-only, and restorable.
