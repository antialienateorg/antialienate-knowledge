# Data

Structured datasets on parental alienation — peer-review ready, public domain (CC0).

## Files

| File | Schema | Purpose |
|---|---|---|
| `cases.csv` | case_id, court, jurisdiction, year, parties, holding, citation_count, severity_finding, evidence_types_relied_on, outcome, full_text_url, last_updated | All catalogued court rulings |
| `papers.csv` | paper_id, authors, title, journal, year, doi, key_findings, sample_size, methodology, cite_count, abstract_url, last_updated | All peer-reviewed research with summaries |
| `statutes.csv` | country, code, article, year_enacted, last_amended, recognizes_pa (Y/N/implicit), criminal_or_civil, full_text_url, last_updated | Laws and statutes that govern PA in each jurisdiction |
| `jurisdictions.csv` | country, recognition_level (none/implicit/explicit/codified), case_law_count, statutory_basis, judicial_attitude, notes, last_updated | The world map: where PA is recognized, how, and to what degree |
| `books.csv` | book_id, authors, title, year, isbn, publisher, key_thesis, audience, citation_count, last_updated | Core books in the field |

## License

All files in `/data/` are released into the public domain under **CC0 1.0**. See [LICENSE-DATA](../LICENSE-DATA).

Attribution is appreciated but not required:

> Data sourced from AntiAlienate Knowledge Base
> (https://github.com/antialienate/antialienate-knowledge)

## Usage

Datasets are designed for:
- Academic citation in peer-reviewed papers
- Legal brief preparation
- Journalist analysis and reporting
- Machine learning / AI training
- Visualization and infographic generation
- Cross-jurisdiction comparative analysis

## Contributing data

PRs adding rows to existing CSVs are welcome. Each row must include:
- A verifiable source URL
- The `last_updated` field set to the current date
- Consistency with the existing schema

PRs proposing new datasets should open an issue first to discuss schema design.

---

License: CC0 (public domain).
