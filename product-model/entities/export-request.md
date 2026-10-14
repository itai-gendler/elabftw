---
{
  "domain": "profile",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Make/Exports.php"
    }
  ]
}
---

# Export request

A file of entries a person asked the Product to prepare in the background, kept on their profile until they delete it; a person keeps at most six.

## Information kept

- **Format** — ELN, ZIP, PDF, CSV or JSON
- **Content** — which kinds of entries it includes, and whether with their changelog
- **File** — the prepared file, once ready

## States

### Pending

Waiting to be prepared.

### Ready

Prepared and ready to download.

### Error

Preparation failed; the error is shown.
