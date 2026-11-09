# Schema

Generated from the exporter's column definitions — do not edit by hand.
Fields marked **AI** were written by Claude from the document itself and can be wrong: always check the original.
In CSV, lists are joined with ` | `; in JSONL they are arrays.

## documents.csv / documents.jsonl

One row per PURSUE document. In JSONL the five entity lists are nested under `entities` (`people`, `agencies`, `locations`, `objects`, `dates`).

| Column | Description |
|---|---|
| `id` | Stable document id; the same id as uapinsight.com/gov/doc/<id>. |
| `release` | PURSUE release id, e.g. pursue-release-7. |
| `release_number` | Release number as an integer; empty if the document isn't tied to a numbered release. |
| `source` | Where we got the record: wargov-uap-csv (war.gov's own index), dvids-videos (AARO videos on DVIDS), zexiro-* (early mirror). |
| `title` | Official title. |
| `doc_type` | pdf, image or video. |
| `agency` | Releasing agency, from war.gov's metadata. |
| `released_at` | Release date (YYYY-MM-DD). |
| `incident_date` | Incident date as given by war.gov (free text). |
| `incident_location` | Incident location as given by war.gov (free text, mixed precision). |
| `original_url` | The original file on war.gov / DVIDS. |
| `uapinsight_url` | The document's page on uapinsight.com. |
| `score` | AI: historical/intelligence significance, 0–10. |
| `summary` | AI: 2–3 sentence factual summary of the document's content. |
| `key_findings` | AI: up to 5 key findings (list). |
| `classification` | AI: classification marking read from the document's stamp. |
| `redaction_level` | AI: how much of the document is redacted. |
| `document_subtype` | AI: most specific document type. |
| `uap_shape` | AI: shape of the observed object as described in the document. |
| `uap_behaviors` | AI: behaviours explicitly described (list). |
| `witness_type` | AI: who or what observed the event. |
| `evidence_types` | AI: types of evidence in or referenced by the document (list). |
| `official_conclusion` | AI: the document's own stated conclusion. |
| `credibility_notes` | AI: limits of the evidence and mundane explanations noted in the document — the skeptical column. |
| `incident_duration` | AI: how long the event lasted, as stated. |
| `government_programs` | AI: government programs named in the document (list). |
| `exceptional_type` | AI: historical, disclosure, high_credibility, or empty. |
| `historical_significance` | AI: why the document is exceptional, if it is. |
| `people` | AI: people named (list). JSONL: entities.people. |
| `agencies_mentioned` | AI: agencies named (list). JSONL: entities.agencies. |
| `locations` | AI: locations named (list). JSONL: entities.locations. |
| `objects` | AI: aircraft and objects named (list). JSONL: entities.objects. |
| `dates_mentioned` | AI: dates mentioned (list). JSONL: entities.dates. |
| `analysis_model` | Claude model that wrote the AI fields. |
| `analyzed_at` | Date of the AI analysis (YYYY-MM-DD). |

## releases.csv

One row per PURSUE release.

| Column | Description |
|---|---|
| `id` | Release id, e.g. pursue-release-7. |
| `release_number` | Release number. |
| `name` | Release name. |
| `released_at` | Release date (YYYY-MM-DD). |
| `document_count` | Number of documents in the release. |
| `agencies` | Releasing agencies (list). |
| `official_url` | The release on war.gov. |
| `uapinsight_url` | The release page on uapinsight.com. |
| `overview` | AI: plain-text overview of what the release contains. |
| `overview_model` | Claude model that wrote the overview. |

## coverage.csv

News articles linked to the release they cover. Titles and links only; the articles themselves are not included and not covered by this dataset's licence.

| Column | Description |
|---|---|
| `release` | The PURSUE release the article covers. |
| `published_at` | Publication date (YYYY-MM-DD). |
| `source_name` | Outlet. |
| `title` | Article title (not covered by our licence). |
| `url` | Link to the article. |
| `uapinsight_url` | The item's page on uapinsight.com. |
