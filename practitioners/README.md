# Practitioners — Open Directory of PA Lawyers & Therapists

> Open-source directory of lawyers and therapists who specialize in parental-alienation cases, with stance characterization (recognition / critique / middle), named cases, and verified contact paths. Designed to be **machine-readable** so downstream directories, referral services, and research teams can ingest the canonical list. CC BY 4.0.

## Why this directory exists

Targeted parents, accused parents, and family lawyers all need to find practitioners with demonstrated PA case experience — and to know what side of the contested field the practitioner is on before retaining them. No comprehensive open list exists today. This is the start of one.

**Distinct from existing referral sites because:**
- Open-source (CC BY 4.0) — adapt, fork, mirror
- Machine-readable parallel (JSON) on every page for downstream ingestion
- Stance characterization is **sourced** — never inferred
- Both recognition-camp and critique-camp practitioners included
- Verified contact paths only — bar profiles, firm websites, court records, named press
- Honest gap-flagging — entries marked "not publicly confirmed" rather than guessed

## Sections

### Lawyers

- **[United States](lawyers/us.md)** — 11 verified entries; JSON: [us.json](lawyers/us.json)
- **United Kingdom** — coming next (Charlotte Proudman, Right to Equality, FNF panel barristers)
- **Canada** — coming next (Bala-associated practitioners; Martinson tradition)
- **Australia / NZ** — coming next (post-2024 reform)
- **EU member states** — coming next (DE / FR / ES / IT / NL / BE)
- **Asia / Africa** — coming next (IN / SG / HK / ZA)

### Therapists

- **United States** — coming next (Family Bridges-affiliated, AB-PA practitioners, trauma-informed alternatives)
- **United Kingdom** — coming next (Family Separation Clinic, NHS-affiliated)
- Other regions — coming as research completes

### Expert Witnesses

- Coming after lawyers + therapists complete — separated because expert-witness reputation is tracked differently (forensic-evaluator track record, Daubert/Frye admissibility decisions)

## How downstream directories can pull from this

Every country page has a parallel `.json` file with the same data in this schema:

```json
{
  "schema_version": "1.0",
  "last_updated": "YYYY-MM-DD",
  "country": "US",
  "type": "lawyers",
  "practitioners": [
    {
      "name": "Full Name, JD",
      "firm": "Firm name",
      "firm_url": "https://...",
      "bar_admissions": ["NY", "FL"],
      "stance": "recognition | critique | middle",
      "stance_source": "URL or citation supporting the stance characterization",
      "named_cases": ["Case v Case, citation"],
      "primary_contact": "email or contact form URL",
      "tier": "1 | 2 | 3",
      "hook": "one-line specific reference for personalised outreach",
      "notes": "any caveats / not-publicly-confirmed flags"
    }
  ]
}
```

To ingest:

```python
import json, urllib.request
url = "https://raw.githubusercontent.com/AntiAlienate/antialienate-knowledge/main/practitioners/lawyers/us.json"
data = json.loads(urllib.request.urlopen(url).read())
for p in data["practitioners"]:
    print(p["name"], p["stance"])
```

The JSON files are the single source of truth. The markdown files are human-readable views.

## Editorial standards

Same standards as [CONTRIBUTING.md](../CONTRIBUTING.md):

- **Primary sources only** — bar admission records, firm websites, published cases, court records, named press
- **Stance characterization must be sourced** — link to a published article, amicus brief, podcast appearance, or court filing that establishes the stance. Never inferred from second-hand description.
- **Working URLs throughout** — every firm URL, every case citation, every contact path must resolve
- **"Not publicly confirmed"** rather than guess for anything that can't be primary-sourced
- **Both sides included** — recognition camp, critique camp, and middle / hybrid practitioners
- **Honest gaps documented** — what we don't yet know about each entry should be flagged in `notes`

## Contributing

PRs welcome adding practitioners with:
- Verified bar admission or licensure
- At least one named case OR published article OR public stance statement
- Working firm URL and contact path
- Sourced stance characterization

PRs that add unverified entries, guess stance, or use second-hand stance attributions will be rejected per the editorial standard.

## Related sections

- [Influencers](../influencers/) — field-defining researchers and clinicians (Bernet, Warshak, Baker, Silberg, etc.) — *different from this directory which is practising lawyers and therapists*
- [Case Studies](../case-studies/) — 26 deeply-investigated cases, many of which name the lawyers and experts who appeared
- [Press → Influencer Outreach](../press/influencer-outreach.md) — separate outreach list focused on field-level academic/clinical figures

---

*CC BY 4.0 · [AntiAlienate.com](https://www.antialienate.com) · Canonical machine-readable JSON URLs at https://raw.githubusercontent.com/AntiAlienate/antialienate-knowledge/main/practitioners/<type>/<country>.json*
