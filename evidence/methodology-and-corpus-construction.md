# Evidence — Methodology and Corpus Construction

A self-reflective methodological synthesis documenting how the AntiAlienate knowledge base v2 corpus is constructed, organised, and verified. Compiled from the corpus itself as a navigational reference for future contributors and downstream agents. CC BY 4.0.

## Four entity types

The corpus operates with four discrete entity types, each with distinct schema and verification standards:

### 1. Practitioner directories
Per-country JSON files at `/practitioners/{therapists,lawyers}/<country>.json` (schema v2.0). Each file carries:
- **jurisdictional_context** — long-prose orientation paragraph
- **structural_findings** — bullet list of corpus-relevant structural observations about the jurisdiction
- **entries[]** — array of individual practitioner / institution entries with stance characterisation
- **excluded[]** — array of regulatory / safeguarding / unverifiable exclusions with documented reasons

Stance enum: `recognition` / `critique` / `middle` / `forensic-evaluator` / `institutional` / `cross-jurisdictional`. Each stance must be primary-source-justified in `stance_notes`.

ID format: `<country_code>.<slug>` — stable across the entity's lifetime.

**Corpus state**: 19 v2 therapist files + 10 v2 lawyer files = 29 v2 practitioner files. 275 verified therapist entries + 146 excluded. 168 verified lawyer entries + 97 excluded. Legacy v1 files preserved as backwards-link continuity (brazil.json + mexico.json + eu.json + latam.json) — superseded by per-country v2 deepenings (br.json + mx.json) + jurisdiction sidecars.

### 2. Case studies
Per-decision JSON files at `/case-studies/<slug>.json` (schema v1.0). Each carries:
- **caption + neutral_citation + jurisdiction_code + decision_date + court + panel + judges**
- **parties + counsel + experts** — anonymised per the deciding court's convention
- **procedural_history + summary + holding + verbatim_quotes + outcome**
- **comparative_jurisprudence** — pointers to related cases (cross-link to slug if extant)
- **subsequent_reception + sources + references + editorial_notes**

Required: author (Alan Markson) + license (CC-BY-4.0). Verbatim quotes must be in original language with translation_en separately.

**Corpus state**: 34 case studies covering jurisdictional spread Spain + Italy + Germany + France + Argentina + Brazil + Mexico + Colombia + UK constituents (E&W + Scotland + NI) + Singapore + Hong Kong + India (5 cases including Delhi HC binomial) + South Africa + Netherlands + Australia + Canada + United States + New Zealand + Poland + Strasbourg supranational (Italian triptych).

### 3. Jurisdiction sidecars
Per-jurisdiction JSON files at `/jurisdictions/<slug>.json` (schema v1.0). Each carries:
- **id + name + jurisdiction_code + legal_system + language**
- **summary + pa_recognition_status** (statutory + apex_court_position + professional_regulator_position)
- **statutory_framework + apex_courts + professional_regulators**
- **anonymisation_convention + key_developments + structural_findings + references + sources + editorial_notes**

Legal-system enum: `common-law` / `civil-law` / `mixed` / `religious-law` / `supranational`.

**Corpus state**: 36 jurisdictions including: EU6 bloc (DE + IT + ES + FR + NL + BE); LATAM5 bloc (AR + BR + MX + CO + CL); British Isles cluster (EWS + SCO + WLS + NIR); Asian apex cluster (IN + SG + HK + JP); African primary set (SA + KE + NG + EG + GH + TZ); Australasia (AU + NZ); North America (US + CA); CEE (PL); supranational (ECHR/COE); UK umbrella + uk-ews alias + 3 regional aggregates (Africa + Asia + UK-Devolved).

### 4. Evidence pages
Per-topic MD files at `/evidence/<slug>.md` — MD-only entity type (no JSON sidecar). Each is a cross-jurisdictional thematic synthesis compiled from the per-jurisdiction + per-case-study sources.

**Corpus state**: 17 evidence pages live (16 thematic + README index). Page set covers all major analytical dimensions of the corpus.

## Cross-link format

Format: `<type>:<id>` where type ∈ {practitioner, case-study, jurisdiction, evidence}.

| Type | ID source | Example |
|---|---|---|
| `practitioner` | `entries[].id` | `practitioner:de.zimmermann-walper-fichtner` |
| `case-study` | `slug` | `case-study:bverfg-1-bvr-1076-23-germany-2023` |
| `jurisdiction` | filename stem | `jurisdiction:germany` |
| `evidence` | filename stem | `evidence:alienating-tactics-as-child-abuse` |

`bin/aa-build refs` resolves every `references` entry across the repo. Broken refs warn (and fail strict-mode CI).

**Cross-link integrity**: ZERO broken refs across entire corpus. Established and maintained throughout the session via systematic slug-mismatch cleanup + creation of missing referenced entities.

## Structural-synthesis approach for evidence pages

Evidence pages operate at three analytic levels:

### Level 1 — Cross-jurisdictional thematic synthesis
Synthesizes a thematic dimension visible across the entire corpus. Pages:
- international-institutional-positions
- alienating-tactics-as-child-abuse
- global-south-womens-rights-critique-register
- childrens-rights-paramountcy-doctrine
- single-judge-authored-apex-decisions
- anonymisation-conventions-across-jurisdictions
- federalism-patterns-and-pa-doctrine-fragmentation
- methodology-and-corpus-construction (this page)

### Level 2 — Regional / structural cluster synthesis
Synthesizes regional or structural-cluster patterns. Pages:
- eu-apex-sequence-2017-2025
- asian-apex-recognition-cluster-2017-2026
- latam5-institutional-anti-sap-comparison

### Level 3 — Focused thematic doctrine synthesis
Synthesizes focused thematic doctrines. Pages:
- evaluator-quality-regulation-across-jurisdictions
- strasbourg-article-8-positive-obligations-doctrine
- statutory-pa-jurisdictions-triple-comparison
- reunification-programmes-and-regulation
- cross-border-parental-abduction-and-pa-intersection
- coercive-control-statutes-and-pa-critique-intersection

## Verification standards

Per `/practitioners/README.md` editorial standards (applied throughout corpus):

- **Primary sources required.** Every claim links to either the deciding court's text, official press release, or the official institutional registry. Secondary literature (NJW, NZFam, LTO, FamRZ, Cairn, SCC Online, scconline, jaacap) is fine for context but marked inline.
- **Verbatim quotes in original language**, with English translation in parentheses or `translation_en` field. Never paraphrase as if verbatim.
- **"Not publicly confirmed" / "not verifiable"** beats a guess. The verification_notes field captures what was checked vs what wasn't.
- **Both camps must be represented.** If a jurisdiction's critique camp is institutionally thin, say so explicitly in `structural_findings`.
- **Exclusions are documented, not silenced.** Regulatory/safeguarding/unverifiable exclusions go in the `excluded` array with `exclusion_reason` and a `primary_source_url`.
- **Anonymisation per the deciding court's convention.** Do not invent identifying details. Honour court anonyms.

## Build pipeline

```bash
python bin/aa-build validate       # JSON Schema validation
python bin/aa-build refs           # cross-link resolution
python bin/aa-build render         # JSON → MD
python bin/aa-build index          # rebuild practitioners/*/README.md
python bin/aa-build aggregate      # mark region-aggregate files as superseded
python bin/aa-build build          # all of the above
python bin/aa-build urls           # opt-in HEAD-check of every URL (slow)
```

CI runs `validate` + `refs` + `render` on every push to `main`. The `render` step also acts as drift detection: if a rendered MD differs from the JSON-derived output, the build fails. This forces JSON-edit-then-render rather than direct MD edits.

## Push pipeline

Commits are made via the Git Data API as atomic multi-file commits (blobs → tree → commit → ref update), so all files in a single push land as ONE Git commit. This avoids race conditions where JSON lands before its rendered MD, triggering per-commit CI failures.

## Discovery endpoint

`/manifest.json` is the canonical discovery endpoint enumerating:
- practitioner files (therapists + lawyers per-country)
- case studies (all slugs)
- jurisdictions (all slugs)
- evidence pages (all filename stems)

Each entry carries a JSON URL + MD URL pointing to the raw GitHub canonical path. Downstream consumers can iterate the manifest programmatically.

## Architectural references

- See `/ARCHITECTURE.md` for schema details + layout + provenance + future-work commitments.
- See `/practitioners/README.md` and `/practitioners/therapists/README.md` for practitioner coverage tables.
- See `/evidence/README.md` for evidence-page indexing.

## Corpus saturation observations

As of generation date the corpus has reached structural-synthesis saturation across major analytical dimensions:
- All major jurisdictions covered with sidecars (36 jurisdictions including EU6 + LATAM5 + British Isles + Asian apex cluster + African primary set + ECHR supranational + UK umbrella + regional aggregates).
- All major apex decisions documented as case studies (34 case studies).
- All major thematic dimensions synthesized as evidence pages (16 thematic + README).
- Cross-link integrity at 100% (zero broken refs).

Future work focuses on (a) per-country v2 deepenings for remaining legacy files + (b) additional case-study coverage for emerging apex jurisprudence + (c) ongoing refresh of jurisdiction sidecars as institutional positions evolve.

## Cross-references
- See `/ARCHITECTURE.md` for architecture spec.
- All companion evidence pages: evidence:international-institutional-positions + evidence:alienating-tactics-as-child-abuse + evidence:eu-apex-sequence-2017-2025 + evidence:asian-apex-recognition-cluster-2017-2026 + evidence:latam5-institutional-anti-sap-comparison + evidence:global-south-womens-rights-critique-register + evidence:evaluator-quality-regulation-across-jurisdictions + evidence:strasbourg-article-8-positive-obligations-doctrine + evidence:statutory-pa-jurisdictions-triple-comparison + evidence:reunification-programmes-and-regulation + evidence:cross-border-parental-abduction-and-pa-intersection + evidence:coercive-control-statutes-and-pa-critique-intersection + evidence:childrens-rights-paramountcy-doctrine + evidence:single-judge-authored-apex-decisions + evidence:anonymisation-conventions-across-jurisdictions + evidence:federalism-patterns-and-pa-doctrine-fragmentation.

---

*Canonical: https://raw.githubusercontent.com/AntiAlienate/antialienate-knowledge/main/evidence/methodology-and-corpus-construction.md*
