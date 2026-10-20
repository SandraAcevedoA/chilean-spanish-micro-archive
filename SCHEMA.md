# Schema Documentation
### Chilean Spanish Micro-Archive

**Schema version:** 0.4 (matches the data, `meta.version` = `0.4`)  
**Data last updated:** 2026-04-03  
**Documentation last updated:** 2026-10-20

---

## Overview

The archive has two data files with the same 50 entries, in the same alphabetical order:

- [`Data/50chilean-spanish-micro-archive.json`](Data/50chilean-spanish-micro-archive.json): the complete, structured version.
- [`Data/50chilean-spanish-micro-archive.csv`](Data/50chilean-spanish-micro-archive.csv): a flat table derived from it.

**The keys are in Spanish, and the Spanish keys are canonical.** This document explains them in English so that readers who do not read Spanish can use the data. It does not define a second, English schema: there are no English aliases for any key.

Each entry has two layers, kept separate by design: **lexical fields**, which describe the word as it is used, and **etymology claims**, which carry their own verification status. A lexical description does not depend on etymological certainty.

---

## JSON

The file is an object with two keys: `meta` and `entries`.

### `meta`

| Key | Type | Description |
|-----|------|-------------|
| `title` | string | Title of the archive, in English and Spanish |
| `description` | string | Short description of the archive |
| `version` | string | Data version (`0.4`) |
| `entry_count` | number | Number of entries (`50`) |
| `last_updated` | string | Date of the last data update (`YYYY-MM-DD`) |
| `license` | string | License of the archive (see [`LICENSE`](LICENSE)) |
| `curator` | string | Curator of the archive |
| `curator_positionality` | string | The curator's position, stated as a methodological datum |
| `methodology` | string | Summary of the curatorial method |
| `nlpgap_framework` | string | What the archive documents in relation to NLPgap |
| `repository` | string | URL of the original repository |
| `primary_sources` | array | Primary sources: objects with `short`, `full` and `url` |
| `secondary_sources` | array | Secondary sources: objects with `short` and `full` |

### Entry fields (`entries[]`)

Every entry has all 14 keys. A text field may be an empty string (`""`) when that dimension has not been documented yet for the term; the key is never omitted.

| Key | Type | Always filled | Description |
|-----|------|---------------|-------------|
| `id` | string | yes | Stable identifier, `CSM-NNN`. It reflects the order in which entries were created, not alphabetical order |
| `término` | string | yes | The word as used in Chilean Spanish. Documented variants go in the same field, separated by ` / ` (for example `Guata / Wata`) |
| `origen` | string | yes | Source language(s) and path of the borrowing, written in English with arrows, for example `Aymara → Quechua → Chilean Spanish`. Uncertainty is stated inside the value (`probable`, `disputed`) |
| `tipo` | string | yes | Type of entry, described in Spanish (for example *préstamo léxico con desplazamiento semántico*) |
| `significado_original` | string | yes | Meaning in the source language, in Spanish |
| `uso_chileno` | string | yes | Meaning or meanings in Chilean Spanish today, in Spanish; polysemous terms list their layers |
| `registro` | string | no | Register and social context of use, in Spanish |
| `capa_colonial` | string | no | The class, historical or colonial coding the word carries, in Spanish |
| `contexto_típico` | string | no | Typical phrases or situations of use |
| `traducción_EN` | string | no | Best functional English equivalent, with notes on what is lost |
| `NLPgap` | string | yes | What language models typically miss about the term, in Spanish |
| `NLPgap_nivel` | string | yes | Level of that gap; see controlled values |
| `fuente` | string | yes | Sources for the entry, including the native speaker corpus (S.A.A.) |
| `claims` | array | yes | One or more etymology claims; see below |

### Etymology claims (`entries[].claims[]`)

| Key | Type | Always filled | Description |
|-----|------|---------------|-------------|
| `claim` | string | yes | The specific etymological claim being evaluated |
| `status` | string | yes | Verification status; see controlled values |
| `method` | string | yes | How the claim was checked; see controlled values |
| `sources` | string | yes | Sources consulted, with edition, year or entry number where available |
| `note` | string | no | What was actually confirmed, or why the claim remains open |

In version 0.4 there are 51 claims across 50 entries: *Pantruca* has two.

---

## CSV

One row per term, in the same order as the JSON. Columns:

| Column | Relation to the JSON |
|--------|----------------------|
| `término`, `origen`, `tipo`, `significado_original`, `uso_chileno`, `registro`, `capa_colonial`, `traducción_EN`, `NLPgap` | Identical to the JSON key of the same name |
| `fuente_primaria` | The bibliographic part of `fuente` |
| `fuente_secundaria` | The native speaker testimony part of `fuente` (S.A.A. corpus) |
| `status_etimología` | `status` of the entry's first claim |

The CSV does not include `id`, `contexto_típico`, `NLPgap_nivel` or the full claims (`claim`, `method`, `sources`, `note`). Use the JSON for those.

---

## Controlled values

### `status` / `status_etimología`

- `verified`: confirmed by at least one solid source with an explicit method.
- `unverified`: analytically productive and supported by native speaker knowledge, but not yet confirmed in primary sources. Unverified does not mean wrong.
- `disputed`: sources conflict, or the claim is contested in the literature.

### `NLPgap_nivel`

- `high`: language models consistently miss culturally significant dimensions.
- `medium-high`: between `high` and `medium`.
- `medium`: models capture the term partially and miss key nuance.
- `low`: models handle the term adequately; the entry is included for completeness.

### `method`

The usual values are:

- `lexicographic`: dictionary or grammar consultation.
- `mixed`: two or more methods combined (lexicographic, academic, corpus attestation, native speaker testimony).
- `pending`: no method applied yet.

When a claim needs a more exact description, `method` holds free text instead, for example `primary lexicographic source + secondary confirmation`. In version 0.4, 6 of the 51 claims do this.

---

## Design notes

**Why Spanish keys?**  
The archive is written from Chilean Spanish, and its keys name what each field holds in the language the data is about. English documentation makes the data usable without turning English into the structure of the archive.

**Why separate lexical fields from claims?**  
What a word means, how it is used and what it encodes socially does not require etymological certainty. A term like *piñén* has documented social meaning whether or not its Mapudungún origin is confirmed in Augusta or Catrileo. Keeping the layers separate means an unverified etymology does not invalidate the entry.

**Why `unverified` instead of leaving the claim out?**  
Leaving it out hides uncertainty. `unverified` makes the state of the claim explicit and queryable. A dataset that shows its uncertainty is more trustworthy than one that looks clean because it erased its doubts.

---

## Version history

| Version | Date | Notes |
|---------|------|-------|
| 0.1 | March 2026 | Prototype schema, 6 entries, README + SCHEMA only. English field names with EN/ES pairs |
| 0.4 | 2026-04-03 (data) · 2026-10-20 (this document) | 50 entries. Spanish keys are canonical; one text field per dimension instead of EN/ES pairs; claims reduced to `claim`, `status`, `method`, `sources` and `note`; CSV with 12 columns |
