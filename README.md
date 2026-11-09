# PURSUE UAP Document Dataset

An open dataset of every document in the U.S. government's **PURSUE** releases — the
*Presidential Unsealing and Reporting System for UAP Encounters* on
[war.gov/UFO](https://www.war.gov/UFO/) — with a structured analysis of each document
and links to the official files.

**Canonical page:** [uapinsight.com/pursue/data](https://uapinsight.com/pursue/data) · Updated daily.

<!-- generated:start -->
**478 documents** (30 image, 298 PDF, 150 video) from **7 PURSUE releases**, 11 agencies, and 133 linked news articles.

Newest release: Release 7 (2026-10-23). Data as of 2026-11-09.
<!-- generated:end -->

## Files

| File | What |
|---|---|
| `data/documents.csv`, `data/documents.jsonl` | One row per document: war.gov metadata plus our analysis — summary, key findings, classification, redaction level, described object shape and behaviour, witness and evidence types, the document's own conclusion, **credibility notes** (limits of the evidence and mundane explanations the document mentions), named programs and entities, significance score. |
| `data/releases.csv` | One row per release, with a plain-text overview of what it contains. |
| `data/coverage.csv` | News articles linked to the release they cover (title, outlet, date, link). |
| `SCHEMA.md` | Every column, described. |

Every row links to the original file on war.gov and to its page on uapinsight.com.

## How it's made — and its limits

- war.gov's own index gives the titles, agencies, dates and file links.
- Claude (Anthropic) read each original PDF, image or video record and wrote the
  analysis fields. **They are machine-generated and can be wrong.** Check the original
  before you rely on a detail.
- The analysis reports what a document says; it does not judge whether a sighting was
  real. Redacted text stays redacted.
- Coverage links are found automatically by matching our news feed to releases.

## Use and citation

Free to use, share and adapt under **CC BY 4.0** — credit **uapinsight.com** with a link
to https://uapinsight.com/pursue/data. The government documents themselves are U.S.
public domain. See [LICENSE](LICENSE) and [CITATION.cff](CITATION.cff).

> uapinsight.com. *PURSUE UAP Document Dataset.* https://uapinsight.com/pursue/data

Also on Hugging Face and Kaggle as `uapinsight/pursue-dataset`.

## About

Built and maintained by [uapinsight.com](https://uapinsight.com), a curated daily
digest of UAP news and government releases, by
[Tomáš Stankovič](https://github.com/tomasstankovic). Corrections and suggestions:
open an issue.
