# Evidence — Documented Exclusions as Corpus Methodology

A self-reflective synthesis on the AntiAlienate corpus's **243 documented exclusions** across the practitioner directories. Compiled to dignify the exclusion ledger as a methodological feature of the corpus rather than treating it as a register of failures. CC BY 4.0.

## Why exclusions are a feature, not a defect

Most public PA practitioner directories operate by silent omission: names that did not pass internal vetting simply do not appear, with no documented reason and no audit trail. The reader cannot tell whether a missing name was never considered, was considered and rejected, or was considered and is pending verification.

The AntiAlienate corpus operates a different epistemic standard. Every entry that was **considered but not included** carries:

- a stable `id` resolvable across the corpus as `practitioner:<id>`,
- a documented `exclusion_reason` that explains why the decision was taken,
- an optional `primary_source_url` pointing to the documentary basis for the decision,
- optional `references` pointing into the broader corpus where the exclusion connects to other evidence.

This converts each exclusion from invisible non-inclusion into a **documented decision with an audit trail**. Future contributors can re-examine each decision, re-verify each candidate, and promote exclusions to entries when verification standards are met. The ledger is a working register, not a graveyard.

## The 243 — by reason cluster

| Cluster | Count | Character |
|---|---:|---|
| Unverifiable | 120 | No public primary-source record located via systematic search across regulator registries, LinkedIn, ResearchGate, university bios, peer-reviewed PubMed/Crossref, and judgment text (court-appointed expert). Distinct from "does not exist" — the practitioner may exist but failed the directory-quality verification threshold. |
| Other | 91 | Mixed: includes structural-non-discrete entities (e.g. Argentine "mediación familiar" practiced via multiple discrete entities), placeholder records, and reasons not cleanly captured by the other clusters. |
| Out-of-scope | 16 | Verified practitioners whose primary professional identity falls outside the receiving file's scope (e.g. attorney appearing in a therapists file, post-traumatic-growth coach appearing in a forensic-evaluator file). These are typically re-routed to the correct file in subsequent passes. |
| Regulatory | 6 | License inactive, struck off, suspended, or otherwise regulatorily out-of-status with the receiving jurisdiction's professional regulator. Primary-source-required. |
| Duplicate | 5 | Practitioner already present under another canonical entry (often a cross-jurisdictional dual-identity case where the primary entry is in another country file). |
| Safeguarding | 5 | Court-documented safeguarding concerns or "ethical-naming safeguard" patterns (LATAM editorial convention) where naming would risk amplifying stigma without epistemic gain. |

## Cluster-by-cluster dignification

### Unverifiable (120)
These are **not** an indictment of the practitioners named. The verification threshold for the directory is intentionally high: HCPC/HPCSA/APBs registration, public practice site, peer-reviewed publication record, or court-appointed expert role in a published judgment. Many practitioners legitimately work outside this footprint — private practice without a website, paper-publication in journals not indexed in CrossRef, registration in a regulator whose register is not publicly searchable. The exclusion records the verification gap; it does not record an evaluative judgment of the practitioner's work.

**What an unverifiable exclusion means**: at the moment of corpus compilation, primary-source verification could not be completed within the directory's editorial standard. The entry remains available for promotion when new sources surface.

### Out-of-scope (16)
These are **dignified relocations**. The practitioner is verified, but the receiving file is wrong. Howard Watson (attorney, PAFSA co-founder) was excluded from `practitioners/therapists/africa.json` because he is primarily an attorney; the same entity would be valid in `practitioners/lawyers/africa.json`. The exclusion is a routing note, not a rejection.

### Safeguarding (5)
The LATAM "ethical-naming safeguard" pattern is **methodologically distinctive within the corpus**. Where a Spanish-language search surfaces a practitioner whose only public artefact is a tabloid-style attack-piece or a name surfacing in a contested family-court proceeding, naming them in the directory would amplify the stigma without producing epistemic value. The exclusion records the editorial decision; the structural finding records the pattern.

### Regulatory (6)
A regulator's published striking-off, suspension, or inactive-registration record is treated as primary-source-sufficient for exclusion with a regulator-citation `primary_source_url`. These are the highest-evidence exclusions in the corpus.

### Duplicate (5)
A practitioner whose canonical entry is in another file appears in a country directory as an excluded reference rather than as a duplicate entry. Sonia Vaccaro is excluded from `practitioners/therapists/ar.json` as `ar.vaccaro-sonia-cross` because her canonical entry is `practitioner:es.vaccaro-sonia` (Spain). The exclusion is a cross-link, not a rejection.

### Other (91)
The largest remaining cluster captures structurally heterogeneous reasoning that resists a single label. Subsequent re-categorisation passes will refine this cluster.

## How to use exclusions

### As referenceable nodes
Every exclusion has a stable `id` resolvable as `practitioner:<id>`. Case studies, evidence pages, jurisdiction sidecars, and other practitioner files can cite an exclusion in their `references` array. The cross-link resolver (`bin/aa-build refs`) treats exclusions and entries as a single namespace.

**Example**: a case study analysing a court-appointed evaluator whose practice is unverifiable in the public record may cite `practitioner:ca.jane-doe` (excluded) to record the audit-trail link, while explaining in `editorial_notes` why the practitioner was not promoted to an entry.

### As a promotion pipeline
An exclusion is not permanent. When primary-source verification becomes available (regulator register comes online, peer-reviewed publication appears, practice site indexed), the exclusion can be **promoted to an entry**:

1. Verify the new primary source against the editorial standard.
2. Move the exclusion JSON from `excluded[]` to `entries[]` in the country file.
3. Add `stance`, `stance_notes`, `verification_notes`, and the new `primary_source_url`.
4. Run `bin/aa-build validate` + `bin/aa-build refs` to confirm integrity.

The audit trail of the exclusion is preserved in git history. The promotion is itself a documented decision.

### As a critique-camp safeguard
Exclusions are not concentrated on one side of the recognition-vs-critique register. The cluster-by-jurisdiction distribution shows exclusions across both recognition-camp and critique-camp practitioners. This is itself a methodological signal: the corpus does not preferentially exclude critique-camp voices, nor does it preferentially exclude recognition-camp voices. Both camps face the same primary-source standard.

## Comparative posture

Most PA-active practitioner directories in the public domain (PASG member registry, BAPAA practitioners list, various national professional-association rosters) operate by inclusion-only with no documented exclusion register. The AntiAlienate corpus's documented-exclusion approach is structurally adjacent to:

- **Cochrane systematic-review methodology**: studies excluded from a meta-analysis are documented with reasons, not silently dropped.
- **Peer-review desk-rejection logs**: journals that publish desk-rejection statistics with cluster-categorised reasons (e.g. "scope mismatch", "methodological concerns", "outside review remit").
- **Open-source security advisory databases (CVE, GHSA)**: every excluded vulnerability report carries a documented "not-applicable" reason rather than disappearing.

In each case the documented exclusion is treated as a feature of epistemic rigour, not as a defect. The AntiAlienate corpus operates the same convention for the practitioner directories.

## Future work

1. **Re-categorisation pass**: the 91-entry "other" cluster will be refined into structurally meaningful sub-clusters in subsequent passes.
2. **Promotion pipeline tooling**: `bin/aa-promote-exclusion <id>` to streamline the JSON-edit-and-validate cycle for promoting exclusions to entries when new sources surface.
3. **Verification-status field**: optional `last_verified` timestamp on exclusions to record when the verification attempt was last made, supporting periodic re-verification cycles.
4. **Cross-link audit**: surface exclusions referenced by case studies / evidence pages in analytics.html with their connecting context.

## Cross-references
- See `/practitioners/README.md` for editorial standards including exclusion documentation rules.
- See `evidence:methodology-and-corpus-construction` for the broader four-entity-type methodology.
- See `analytics.html` for the full 243-row exclusion table with reasons and source URLs.

---

*Canonical: https://raw.githubusercontent.com/AntiAlienate/antialienate-knowledge/main/evidence/documented-exclusions-as-corpus-methodology.md*
