---
title: "Case File — Recommended Folder Structure"
slug: case-file-folder-structure
type: template
last_verified: "2026-05-25"
license: "CC BY 4.0"
---

# Case File — Recommended Folder Structure

Three years of evidence accumulates fast. A disciplined folder structure means you can find any document in seconds, share read access with your lawyer cleanly, and survive a laptop change without losing the file.

## The structure

```
case-file/
├── README.md                          ← what's where, last updated
├── 00-orders/                          ← all court orders, named [YYYY-MM-DD]-[order-type].pdf
├── 01-pleadings/                       ← every filing, named [YYYY-MM-DD]-[party]-[filing-type].pdf
├── 02-correspondence/                  ← solicitor / barrister letters
│   ├── outgoing/
│   └── incoming/
├── 03-evidence/
│   ├── contact-log.xlsx                ← the master spreadsheet (linked from value card)
│   ├── chronology.md                   ← human-readable narrative chronology
│   ├── 2024-01/                        ← per-month source files
│   │   ├── sms-2024-01-14.png
│   │   ├── email-2024-01-15.eml
│   │   └── voicemail-2024-01-16.m4a
│   ├── 2024-02/
│   └── …
├── 04-third-party-records/
│   ├── school/                         ← GDPR SAR responses + ongoing
│   ├── medical/                        ← GP, paediatrician, hospital
│   ├── police/                         ← CAD logs, incident reports
│   └── social-care/                    ← any LA referrals + responses
├── 05-third-party-statements/         ← witness statements
├── 06-expert-reports/
│   ├── cafcass-gal/                    ← appointed officer reports
│   ├── psychological/                  ← court-appointed + retained
│   └── other/
├── 07-financial/                       ← only if relevant to the case
├── 08-authorities/                     ← cases + statutes + articles you cite
├── 09-bundles/                         ← prepared court bundles, by hearing date
└── 99-archive/                         ← old/superseded material
```

## Naming conventions

- Dates always **YYYY-MM-DD** at the start. This sorts chronologically by default.
- All filenames lowercase, hyphenated. No spaces.
- Each file's name should let you understand what it is without opening.

Good: `2024-03-14-mother-objection-to-contact-application.pdf`
Bad: `Document1 (3).pdf`

## Sync strategy

- **Primary store:** local laptop drive (encrypted at rest — FileVault on Mac, BitLocker on Windows).
- **Cloud sync:** Dropbox / OneDrive / Google Drive — shared folder with your lawyer.
- **Cold backup:** monthly to an external drive kept off-site.
- **Court-bundle archive:** every completed bundle gets PDF-archived under `09-bundles/[hearing-date]/`.

## What lives outside the case file

- Anything personal / unrelated to the case (your own medical records that aren't relevant, work documents, etc.).
- Your contact log working draft (keep that in the spreadsheet itself, with a dated PDF export saved into `03-evidence/` when stable).

## Sharing read access with your lawyer

Most lawyers use Dropbox, OneDrive, or a dedicated client portal. Give them read access to the top-level folder. They can read everything; only you write.

When a lawyer reads a file, they often want to annotate it. Either:
- Use a tool that supports comments (Dropbox Paper, Google Drive, OneDrive Office).
- OR create a parallel `case-file/_lawyer-notes/` folder they can write into.

## Related

- [Contact log spreadsheet](./contact-log-spreadsheet.md)
- [Court bundle structure](./court-bundle-structure.md)
- [GDPR Art 15 — school SAR](./gdpr-art-15-school-sar.md)
- [GDPR Art 15 — medical SAR](./gdpr-art-15-medical-sar.md)


---

**Disclaimer.** This is a starter template, not legal advice. Adapt to your jurisdiction and case facts. Have a licensed practitioner review before filing. Statutes and procedural rules vary and update — verify against primary source.

— [AntiAlienate.com](https://www.antialienate.com) · CC BY 4.0
