# Chilean Spanish Micro-Archive
### *A bilingual annotated lexicon of Chilean Spanish terms with indigenous substrate*

**Status:** Prototype · 6 entries · active development  
**Maintainer:** Sandra D. Acevedo Alvarado · [acevedology.com](https://acevedology.com)  
**License:** CC BY-NC-SA 4.0  

---

## What this is

A small, carefully documented lexicon of Chilean Spanish words that carry Mapudungún, Quechua, or Aymara substrate — terms where meaning, class coding, and colonial history are compressed into everyday use.

This is not a comprehensive dictionary. It is a **proof-of-concept dataset** designed to demonstrate:

- How culturally situated NLP evaluation data should be structured
- What gets lost when indigenous-origin vocabulary is processed without cultural context
- How a responsible dataset handles uncertainty (rather than hiding it)

Each entry is bilingual (EN/ES) and includes a **verification-as-claims layer**: etymologies are treated as objects with status, method, and sources — not as settled facts.

---

## Why this matters for NLP

Large language models trained predominantly on English and standardized Spanish systematically underrepresent the cultural and sociolinguistic weight of Latin American vocabulary. This gap is not random — it reflects whose knowledge is considered data.

Chilean Spanish is a particularly rich case: it contains hundreds of words from Mapudungún and Andean languages (Quechua, Aymara) that have been absorbed, resemantized, or stripped of their original meaning through colonial contact. LLMs typically:

- Return the surface chilenismo meaning without indigenous etymology
- Miss class-coded or historically charged dimensions of common words
- Cannot identify when a term encodes colonial semantic violence (e.g. a sacred ritual word degraded to mean "gossip")
- Conflate distinct indigenous-origin words under generic "regional variant" labels

This archive is part of a larger research project on culturally situated NLP evaluation for Latin American Spanish. See: [NLPgap Research](https://acevedology.com/research.html)

---

## Corpus scope

| Parameter | Value |
|-----------|-------|
| Languages documented | Chilean Spanish, Mapudungún, Quechua, Aymara |
| Entry types | Lexical borrowings, semantic shifts, toponyms, polysemous terms |
| Annotation | Bilingual (EN/ES), register, social coding, NLPgap relevance |
| Verification | Claims-based (verified / unverified / disputed) |
| Current entries | 6 (prototype) |
| Target entries | 100+ |
| Primary source | Native speaker corpus (S.A.A.) |

---

## Repository structure

```
chilean-spanish-micro-archive/
│
├── README.md                  ← this file
├── SCHEMA.md                  ← field definitions and controlled vocabulary
├── METHODOLOGY.md             ← editorial decisions, verification protocol
│
├── data/
│   ├── entries.csv            ← flat tabular format (coming soon)
│   └── entries.json           ← structured format with claims (coming soon)
│
└── sources/
    └── SOURCES.md             ← bibliography and verification status by source
```

---

## Schema overview

Each entry contains two layers:

**1. Lexical fields**
- `term`, `language_of_origin`, `entry_type`
- `original_meaning` (EN + ES)
- `meaning_in_use` (EN + ES)
- `register`, `encoded_social_meaning`, `typical_context`
- `functional_translation_en`, `cultural_notes`
- `nlpgap_relevance`, `source`

**2. Etymology claims** (one or more per entry)
- `claim_type`, `claim_text`
- `verification_status`: `verified | unverified | disputed`
- `verification_method`: `lexicographic | academic | corpus-attestation | mixed`
- `sources` (list with edition/year where available)
- `verification_note`

Full field definitions: see [SCHEMA.md](SCHEMA.md)

---

## Current entries

| Term | Origin | Entry type | Status |
|------|--------|------------|--------|
| Piñén | Mapudungún | Lexical borrowing | etymology unverified |
| Puma | Mapudungún | Lexical borrowing (global) | etymology unverified |
| Cahuín | Mapudungún | Borrowing + semantic shift | etymology unverified |
| Ñuñoa | Mapudungún | Toponym | etymology unverified |
| Luche | Mapudungún / Quechua (disputed) | Polysemous term | species verified · etymology disputed |
| Cochayuyo | Quechua | Borrowing via coastal culture | species verified · etymology unverified |

*Verification against primary sources (Augusta 1916, Catrileo 1996, Ayacucho Quechua dictionaries) is in progress.*

---

## Verification triad

Following the methodology proposed in this project, etymological claims are evaluated against three source types:

1. **Lexicographic** — Mapudungún and Quechua dictionaries and grammars (Augusta 1916, Catrileo 1996, Zúñiga 2000, etc.)
2. **Corpus attestation** — Real-use examples in press, recipes, institutional documents, Chilean Spanish corpora
3. **Academic** — Peer-reviewed papers and theses for conflictive or high-stakes etymologies

A claim is `verified` if supported by at least one solid source; `disputed` if sources conflict; `unverified` if supported by native speaker knowledge but not yet confirmed in primary sources.

**Unverified ≠ wrong.** It means the claim is honest about where it stands.

---

## How to cite

```
Acevedo Alvarado, Sandra D. (2025–). Chilean Spanish Micro-Archive: 
A bilingual annotated lexicon with indigenous substrate. 
Prototype dataset. acevedology.com. 
https://gitlab.com/acevedos/chilean-spanish-micro-archive
```

---

## Contact

Sandra D. Acevedo Alvarado  
Independent Researcher · Culturally Situated AI Systems  
[acevedology.com](https://acevedology.com) · [contact](https://acevedology.com/contact.html)