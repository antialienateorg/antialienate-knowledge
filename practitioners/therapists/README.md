# Practitioners — Therapists

Open directory of therapists, psychologists, and clinical social workers who work parental-alienation cases — with stance characterization, named programmes/publications, and verified contact paths. CC BY 4.0.

## Coverage

| Country / Region | Markdown | Machine-readable JSON | Schema | Entries |
|---|---|---|---|---|
| **United States** | [us.md](us.md) | [us.json](us.json) | **v2.0** | 19 verified + 12 excluded |
| **United Kingdom (E&W)** | [uk.md](uk.md) | [uk.json](uk.json) | **v2.0** | 12 verified + 8 excluded |
| **Canada** | [ca.md](ca.md) | [ca.json](ca.json) | **v2.0** | 17 verified + 16 excluded |
| **Australia** | [au.md](au.md) | [au.json](au.json) | **v2.0** | 12 verified + 9 excluded |
| **New Zealand** | [nz.md](nz.md) | [nz.json](nz.json) | **v2.0** | 16 verified + 3 excluded |
| **Germany** | [germany.md](germany.md) | [germany.json](germany.json) | **v2.0** | 16 verified + 9 excluded |
| **Spain** | [spain.md](spain.md) | [spain.json](spain.json) | **v2.0** | 16 verified + 3 excluded |
| **France** | [france.md](france.md) | [france.json](france.json) | **v2.0** | 17 verified + 6 excluded |
| **Italy** | [it.md](it.md) | [it.json](it.json) | **v2.0** | 19 verified + 4 excluded |
| **Netherlands** | [nl.md](nl.md) | [nl.json](nl.json) | **v2.0** | 17 verified + 5 excluded |
| **Belgium** | [be.md](be.md) | [be.json](be.json) | **v2.0** | 17 verified + 6 excluded |
| **EU (DE/FR/ES/IT/NL/BE)** | [eu.md](eu.md) | [eu.json](eu.json) | v1.0 (legacy) | 22 verified across 6 countries (superseded by per-country v2 deepenings) |
| **Brazil** (focused v2 institutional regulators) | [br.md](br.md) | [br.json](br.json) | **v2.0** | 3 institutional entries (CFP NT 4/2022 + CFESS + IBDFAM) |
| **Brazil** (legacy v1) | [brazil.md](brazil.md) | [brazil.json](brazil.json) | v1.0 (legacy) | 15 verified + 7 excluded — superseded by br.json focused v2 + jurisdiction:brazil sidecar |
| **México** (focused v2 institutional regulators) | [mx.md](mx.md) | [mx.json](mx.json) | **v2.0** | 4 institutional entries (SMP silente documentado + CNDH + INMUJERES + DDHPO Oaxaca promovente AI 11/2016) |
| **Mexico** (legacy v1) | [mexico.md](mexico.md) | [mexico.json](mexico.json) | v1.0 (legacy) | 15 verified + 9 excluded — superseded by mx.json focused v2 + jurisdiction:mexico sidecar |
| **Argentina** | [ar.md](ar.md) | [ar.json](ar.json) | **v2.0** | 14 verified + 9 excluded |
| **Colombia** | [co.md](co.md) | [co.json](co.json) | **v2.0** | 13 verified + 6 excluded |
| **Chile** | [cl.md](cl.md) | [cl.json](cl.json) | **v2.0** | 16 verified + 7 excluded |
| **LATAM (BR/MX/AR/CO/CL)** | [latam.md](latam.md) | [latam.json](latam.json) | v1.0 (legacy) | 18 verified across 5 countries (superseded by per-country v2 deepenings) |
| **India** | [india.md](india.md) | [india.json](india.json) | **v2.0** | 14 verified + 21 excluded |
| **Asia (non-IN: SG/HK/JP/KR)** | [asia.md](asia.md) | [asia.json](asia.json) | **v2.0** | 8 verified + 16 excluded |
| **Africa (ZA + KE/NG/EG)** | [africa.md](africa.md) | [africa.json](africa.json) | **v2.0** | 20 verified + 6 excluded |

**19 country/regional files are now schema v2.0 (JSON-canonical).** The `.md` is rendered from the JSON by `bin/aa-build render`. The legacy v1.0 format is largely migrated; brazil.json + mexico.json + eu.json + latam.json remain as backwards-link continuity legacy files superseded by per-country v2 deepenings + jurisdiction sidecars. See [/ARCHITECTURE.md](../../ARCHITECTURE.md) for the architecture spec and `/manifest.json` for the canonical enumeration for downstream consumers.

**LATAM5 v2 institutional coverage complete** (AR + BR + CL + CO + MX all with v2 institutional / professional-regulator entries + jurisdiction sidecars). Brazil + Mexico operate as focused-institutional v2 with deeper individual-clinician deepening pending in legacy v1 files.

**LATAM5 bloc fully deepened** (BR / MX / AR / CO / CL all standalone). The legacy `latam.md` aggregate is now superseded by the per-country files — kept for backwards-link continuity.

**EU6 bloc fully deepened** (DE / FR / ES / IT / NL / BE all standalone). The legacy `eu.md` aggregate is now superseded by the per-country files — kept for backwards-link continuity.

## Structural findings

### LATAM5 institutional anti-SAP comparison

| Country | Professional regulator | State authorities | Apex court | Statutory hook |
|---|---|---|---|---|
| **Brazil** | CFP NT 4/2022 + CFESS | — | — | Lei 12.318/2010 (codifies AP — recognition direction) |
| **Mexico** | Soc. Mex. Psicología: **silent** | CNDH + INMUJERES | SCJN AI 11/2016 (Oaxaca) — invalidated only *automaticity* | CDMX 323 Septimus *derogated* 2017; state-level remains |
| **Argentina** | FePRA Pronunciamiento 14.12.2019 + 7 provincial Colegios | ASAPMI + Defensoría del Pueblo CABA | CSJN: **no AP/SAP apex ruling** | CCyC art. 671 + Ley 24.270/1993 (indirect) |
| **Colombia** | COLPSIC Posición Gremial 16.11.2023 (deliberate pivot from 2017 recognition-leaning) | ICBF + MinSalud + Procuraduría + Defensoría | Corte Constitucional **T-526/2023** | Ley 1098/2006 + Ley 21.430 (children's rights) |
| **Chile** | CdPCh: **silent** | ANMM + SernamEG + Cámara de Diputadas (Boletín 10.516-18 rejected 58-45-26, abril 2024) | Corte Suprema: **no proscription** (then-vocera Vivanco publicly defended SAP, Jan 2023) | Ley 21.675/2024 substitutes *violencia vicaria* for SAP-as-VIF |

- **Chile — inverted institutional pattern**: The CdPCh has issued NO PA-specific gremial position — silence of the professional regulator is itself the structural anomaly. Rejection runs through Executive (SernamEG / Min. Antonia Orellana) + ANMM (Verónica Vymazal) + Legislature (Cámara de Diputadas rejected Boletín 10.516-18 in April 2024) + Ley 21.675/2024 — NOT through the psychology college or constitutional court. **Two institutional silences converge: CdPCh + Defensoría de la Niñez**. The Corte Suprema is NOT a critique anchor — its then-vocera Ángela Vivanco publicly defended SAP in January 2023; CS Sala Cuarta has incorporated gender perspective + *violencia vicaria* (Ley 21.675/2024) but never proscribed SAP. Chile lacks a T-526/23 equivalent. Recognition camp is **geographically decentralized** (Concepción, Antofagasta, Arica), inverse to metropolitan critique camp. Nelson Zicavo (UBB Concepción) ZICAP scale is unusually strong recognition instrument development for LATAM. Institutional 7 / Critique 5 / Recognition 3 / Middle 1.
- **Colombia — widest institutional critique coalition in LATAM**: five converging state authorities (COLPSIC + ICBF + MinSalud + Procuraduría General + Corte Constitucional) all cited as convergent técnico/jurisprudential concepts in **T-526/2023**. COLPSIC 2017 was recognition-leaning; the 2023 Posición is a deliberate institutional pivot.
- **Belgium — critique anchor at gender-equality regulator, not psychology regulator**: The **IEFH/IGVM Recommandation 2023/001** is structurally unique in EU6 — a single federal bilingual (NL+FR) gender-equality regulator with an explicit institutional position that *"le syndrome d'aliénation parentale ne peut être utilisé pour minimiser la violence entre (ex-)partenaires."* Belgium is the only EU6 jurisdiction where the critique-camp position is articulated at federal-regulator level rather than only at professional-association or judicial level. Combined with BFP-BPF + Psychologencommissie silence (parallel to the NL pattern), the Belgian signature is: critique-camp institutional anchor lives at the gender-equality regulator, not the psychology regulator. No Cour de cassation apex PA-specific ruling exists. Critique 5 / Middle 5 / Recognition 2 / Institutional 5.
- **Netherlands — positional weight in documents, not associations**: Neither NIP (Nederlands Instituut van Psychologen) nor NVvP (Nederlandse Vereniging voor Psychiatrie) has issued any public PA/PAS position statement. Dutch debate is anchored by three documents: (1) **NJI Richtlijn Scheiding** (2020, van der Valk); (2) **Expertteam Ouderverstoting** advisory report (Jan 2021, chair: Catrin Finkenauer, UU); (3) **Kinderombudsman advisory KOM003/2014**. Structurally distinct from IT / ES / BR / AR / CO patterns where professional associations have anchored the debate. The Lorentzhuis programme (van Lawick + Visser, *Kinderen Uit de Knel*) **explicitly rejects** the *ouderverstoting* terminology as suggestive of "a conscious and aggressive process" and prefers *geblokkeerde ouder-kindrelaties* — classified middle, not recognition. Critique 3 / Recognition 1 / Middle 6 / Institutional 7.
- **Italy — strongest EU statutory-and-caselaw stance against PAS-CTU**: Cassazione I Civile ordinanze **13217/2021 → 9691/2022 → 4595/2025** + **Riforma Cartabia (D.lgs. 149/2022)**. See [Cassazione 13217/2021](../../case-studies/cassazione-13217-2021-italy.md) + [Cassazione 9691/2022](../../case-studies/cassazione-9691-2022-italy.md) case studies.
- **Argentina — institutional inadmission without statutory inadmission (inverse of Spain)**: densest LATAM critique routed through *colegios profesionales*. The 2024 Milei restructuring shifted the anchor from federal executive to universities + colegios + civil society.
- **Brazil and Spain are the world's only two statutory PA jurisdictions — pointed in opposite directions**.
- **France — institutionally asymmetric**: no French *autorité publique* has ever endorsed SAP.
- **Germany — institutional inflection 2023-2026**: BVerfG 17.11.2023 – 1 BvR 1076/23 + DJI 2023 + OLG Frankfurt 7 UF 88/25. See [BVerfG case study](../../case-studies/bverfg-1-bvr-1076-23-germany-2023.md) + [OLG Frankfurt case study](../../case-studies/olg-frankfurt-7-uf-88-25-germany-2026.md).
- **Mexico — uniquely fragmented**: Soc. Mex. Psicología issued no public PA-specific position.
- **Spain — terminological-arbitrage gap**: LOPIVI targets only the SAP label by name.
- **Brazil**: only LATAM jurisdiction where institutional critique pole and clinical recognition pole are roughly equal in institutional weight.
- **India**: ZERO individual critique-camp clinicians with peer-reviewed PA-critique publication.

## Editorial standards

See [../README.md](../README.md). Primary-source verification on every entry; stance characterization must be sourced.

## Excluded practitioners (regulatory / safeguarding disclosure)

- **Randy Rand, EdD** (US) — CA psychology license inactive since 2009. See [us.md](us.md).
- **Melanie Gill** (UK) — unregulated; *Re Y* [2026] EWFC 38 set aside her findings. See [uk.md](uk.md).
- **Reinhart Wolff** (DE) — excluded for safeguarding reasons. See [germany.md](germany.md).

---

*Canonical JSON: `https://raw.githubusercontent.com/AntiAlienate/antialienate-knowledge/main/practitioners/therapists/<country>.json`*
