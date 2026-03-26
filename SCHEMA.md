# Schema Documentation
### Chilean Spanish Micro-Archive

**Version:** 0.1 (prototype)  
**Last updated:** March 2026  

---

## Overview

Each entry in this dataset consists of two layers: **lexical fields** and **etymology claims**. The two layers are kept separate by design — lexical description does not depend on etymological certainty.

---

## Lexical fields

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `id` | string | yes | Unique identifier, e.g. `SAA-001` |
| `term` | string | yes | The word as used in Chilean Spanish |
| `variant_spelling` | string | no | Documented orthographic variants only — not transcription artifacts |
| `language_of_origin` | string | yes | Primary source language(s) |
| `entry_type` | string | yes | See controlled vocabulary below |
| `original_meaning_en` | string | yes | Meaning in source language, in English |
| `original_meaning_es` | string | yes | Meaning in source language, in Spanish |
| `meaning_in_use_en` | string | yes | Meaning as used in Chilean Spanish, in English |
| `meaning_in_use_es` | string | yes | Meaning as used in Chilean Spanish, in Spanish |
| `register` | string | yes | See controlled vocabulary below |
| `encoded_social_meaning_en` | string | yes | Class, historical, or ideological coding, in English |
| `encoded_social_meaning_es` | string | yes | Class, historical, or ideological coding, in Spanish |
| `typical_context_en` | string | yes | Example phrases or situations of use, in English |
| `typical_context_es` | string | yes | Example phrases or situations of use, in Spanish |
| `functional_translation_en` | string | yes | Best English equivalent, with notes on gaps |
| `cultural_notes_en` | string | no | Additional cultural, historical, or linguistic context, in English |
| `cultural_notes_es` | string | no | Additional cultural, historical, or linguistic context, in Spanish |
| `nlpgap_relevance` | string | yes | See controlled vocabulary below |
| `source` | string | yes | Primary source for the entry (see SOURCES.md) |

---

## Etymology claims

Each entry may have one or more claims. Claims are stored as an array.

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `claim_type` | string | yes | Always `"etymology"` for this version |
| `claim_text` | string | yes | The specific claim being evaluated |
| `verification_status` | string | yes | `verified`, `unverified`, or `disputed` |
| `verification_method` | string | yes | See controlled vocabulary below |
| `sources` | array | yes | List of sources consulted (empty list is valid) |
| `verification_note` | string | yes | 1–3 sentences: what was actually confirmed, not just "read the book" |

---

## Controlled vocabularies

### `entry_type`
- `lexical-borrowing` — word adopted from an indigenous language into Chilean Spanish
- `lexical-borrowing-semantic-shift` — borrowing where meaning changed significantly in transit
- `toponym` — place name of indigenous origin preserved in urban/administrative use
- `polysemous` — single word with two or more distinct meanings in Chilean Spanish
- `calque` — structural loan (meaning borrowed, not form)

### `register`
- `colloquial` — everyday informal speech
- `familiar` — intimate/family contexts
- `colloquial-familiar` — both apply
- `neutral` — no strong register marking
- `technical` — specialized domain (biology, etc.)
- `archaic` — receding from active use

### `nlpgap_relevance`
- `high` — LLMs consistently miss culturally significant dimensions
- `medium` — LLMs partially capture the term but miss key nuance
- `low` — LLMs handle the term adequately; entry included for corpus completeness
- `pending` — not yet evaluated against LLM output

### `verification_status`
- `verified` — confirmed in at least one solid primary source
- `unverified` — supported by native speaker knowledge; primary source confirmation pending
- `disputed` — sources conflict, or the claim is contested in the literature

### `verification_method`
- `lexicographic` — dictionary or grammar consultation
- `academic` — peer-reviewed paper or thesis
- `corpus-attestation` — confirmed in real-use examples (press, documents, corpora)
- `mixed` — two or more methods combined
- `pending` — method not yet applied

---

## Design notes

**Why separate lexical fields from claims?**  
Lexical description (what a word means, how it's used, what it encodes socially) does not require etymological certainty. A term like *piñén* has documented social meaning regardless of whether its Mapudungún origin is confirmed in Augusta or Catrileo. Keeping the layers separate means an unverified etymology does not invalidate the entry.

**Why bilingual fields (EN + ES)?**  
The dataset is designed for audiences who may not read Spanish, while preserving Spanish-language precision for terms where translation is inherently lossy. Many entries have no exact English equivalent — the English field documents this gap explicitly rather than flattening it.

**Why `unverified` instead of just leaving fields empty?**  
Empty fields hide uncertainty. `unverified` makes the epistemological state of the claim explicit and queryable. A dataset that shows its uncertainty is more trustworthy than one that appears clean because it erased its doubts.

---

## Version history

| Version | Date | Notes |
|---------|------|-------|
| 0.1 | March 2026 | Prototype schema, 6 entries, README + SCHEMA only |
