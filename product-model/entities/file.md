---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Uploads.php"
    }
  ]
}
---

# Attached file

A file attached to an experiment or resource, listed among its attached files, including the timestamp and signature archives the Product attaches itself.

## Information kept

- **Name** — the original file name
- **Comment** — a description; timestamp and signature archives say who made them
- **Immutable** — whether it is a timestamp or signature archive that can never be edited, replaced or deleted on its own

## States

### Normal

Shown in the entry's attached files.

### Archived

Hidden unless archived files are shown; timestamp and signature archives start here.

### Deleted

Removed from the entry's attached files.
