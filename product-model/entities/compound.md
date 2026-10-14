---
{
  "domain": "compounds",
  "relations": [
    {
      "entity": "experiment",
      "verb": "appears-in",
      "cardinality": "many-to-many"
    },
    {
      "entity": "resource",
      "verb": "appears-in",
      "cardinality": "many-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Models/Compounds.php"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/user-guide/compounds.md"
    }
  ]
}
---

# Compound

A chemical compound in the instance-wide compounds database, which every signed-in person sees and entries can refer to.

## Information kept

- **Name** — its name, the only required property
- **CAS number** — its CAS registry number
- **PubChem CID** — its PubChem compound identifier
- **SMILES** — its SMILES representation, used for structure search
- **InChI** — its InChI and InChIKey
- **Molecular formula** — its molecular formula and weight
- **Hazards** — its safety classification: corrosive, explosive, flammable, toxic, controlled substance and the like

## States

### Normal

Listed in the compounds database.

### Deleted

Removed from the compounds database.
