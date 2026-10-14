---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Steps.php"
    }
  ]
}
---

# Step

An action to take for an experiment, resource or template; the next unfinished one is shown under the entry's title in lists and in the to-do list.

## Information kept

- **Text** — what has to be done
- **Deadline** — an optional due date, with an optional reminder
- **Locked** — whether it came locked from a template
- **Finished at** — when it was last ticked

## States

### Unfinished

Still to do.

### Finished

Ticked as done; its deadline and reminder are cleared.
