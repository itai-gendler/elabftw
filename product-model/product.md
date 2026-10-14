---
{
  "id": "elabftw",
  "summary": "An electronic lab notebook for research teams: experiments, a database of resources, templates, statuses, trusted timestamps, signatures and team permissions on one self-hosted instance.",
  "category": "electronic-lab-notebook",
  "tags": [
    "lab-notebook",
    "research",
    "timestamping",
    "traceability"
  ],
  "authors": [
    {
      "name": "eLabFTW project",
      "url": "https://github.com/elabftw/elabftw"
    }
  ],
  "license": "AGPL-3.0-or-later",
  "languages": [
    "en-GB",
    "en-US",
    "ca-ES",
    "cs-CZ",
    "de-DE",
    "el-GR",
    "es-ES",
    "et-EE",
    "fi-FI",
    "fr-FR",
    "hr-HR",
    "id-ID",
    "it-IT",
    "ja-JP",
    "ko-KR",
    "nl-BE",
    "pl-PL",
    "pt-BR",
    "pt-PT",
    "ru-RU",
    "sk-SK",
    "sl-SI",
    "sv-SE",
    "uk-UA",
    "uz-UZ",
    "zh-CN",
    "zh-TW"
  ],
  "limitations": [
    "Deleting an experiment or resource moves it to the trash; nothing is erased and it can be restored.",
    "Visibility additions only widen access: teams, user groups and users added to an entry never narrow its base visibility.",
    "A timestamp proves what an entry held when it was made; it does not freeze the entry, and later changes need a new timestamp.",
    "Trusted timestamps come from external Time Stamping Authorities or the Bloxberg blockchain; the Product issues none itself."
  ],
  "references": [
    {
      "kind": "doc",
      "role": "intent",
      "target": "README.md"
    },
    {
      "kind": "doc",
      "role": "intent",
      "target": "documentation/docs/usage/intro.md"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "composer.json"
    }
  ]
}
---

# eLabFTW

eLabFTW is an electronic lab notebook that several research teams share on one installation. Members record experiments and keep a database of resources such as antibodies, plasmids, chemicals and equipment, start both from templates, and track them with team-defined statuses, categories, tags and steps. Each entry carries its own read and write permissions, can be locked, archived, deleted and restored, and keeps a changelog and revisions of its main text. Entries can be timestamped through a trusted Time Stamping Authority or a blockchain and signed with personal keys. Team Admins decide what members may create and manage membership; Sysadmins configure the instance and read its audit log.

## Intent

eLabFTW exists so research teams can store and organize their experiments and the things they use, from the browser, on a self-contained server that does not leak data to third parties. Hosting several teams on one installation lets an institute serve everyone in one place, and timestamping, signatures, permissions and audit records make it suitable for sensitive research results and for organizations that need traceable, reproducible processes.
