# Chilean Spanish Micro-Archive
### *A bilingual annotated lexicon of Chilean Spanish terms with indigenous substrate*

**Status:** Prototype · 24 entries · active development  
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
| Entry types | Lexical borrowings, semantic shifts, toponyms, polysemous terms, hybrid formations |
| Annotation | Bilingual (EN/ES), register, social coding, NLPgap relevance |
| Verification | Claims-based (verified / unverified / disputed) |
| Current entries | 24 (prototype) |
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
│   ├── chilean-spanish-micro-archive.csv    ← flat tabular format (24 entries)
│   └── chilean-spanish-micro-archive.json   ← structured format with claims layer
│
└── sources/
    └── SOURCES.md             ← bibliography and verification status by source
```

---

## Primary sources

All three primary sources are held at the Biblioteca Nacional de Chile, digitized, and available as public domain through [Memoria Chilena](https://www.memoriachilena.gob.cl).

**Lenz, Rodolfo (1910).** *Diccionario etimológico de las voces chilenas derivadas de lenguas indígenas americanas.* Santiago: Universidad de Chile / Imprenta Universitaria. Biblioteca Nacional de Chile MC0038306.  
→ [memoriachilena.gob.cl](https://www.memoriachilena.gob.cl/602/w3-article-8193.html)  
The foundational etymological dictionary of Chilean Spanish indigenous borrowings. Principal verification source for Mapudungún and Quechua etymologies.

**Manquilef, Manuel (1911).** *Comentarios del pueblo araucano (La faz social).* Santiago: Imprenta Cervantes. Published in *Anales de la Universidad de Chile*, tomo CXXVIII. Biblioteca Nacional de Chile MC0008915.  
→ [memoriachilena.gob.cl](https://www.memoriachilena.gob.cl/602/w3-article-8192.html)  
The first scientific work published by a Mapuche author in the Anales de la Universidad de Chile. Used here for documentation of Mapuche social practices, material culture, and a word list of Chilean Spanish borrowings from Mapudungún.

**Valdivia, Luis de (1684).** *Arte y gramática general de la lengua que corre en todo el Reyno de Chile: con un vocabulario, y confesionario.* Sevilla: Thomás López de Haro. Biblioteca Nacional de Chile MC0013038.  
→ [memoriachilena.gob.cl](https://www.memoriachilena.gob.cl/602/w3-article-8485.html)  
The earliest colonial grammar of Mapudungún. Consulted primarily as negative evidence: what it does not record is as methodologically significant as what it does.

---

## Secondary sources

**González Retamal, Cristián (2018).** *Vitalidad y mortandad léxica de los mapuchismos.* Universidad de Chile.  
Lexical vitality study of Mapuche borrowings in Chilean Spanish; includes onomasiological and semasiological recognition data across two age groups (20–50 and 50–80) in two communities.

**Valencia Alba, Alba (1977).** Voces amerindias en el español culto oral de Santiago de Chile. *Boletín de Filología*, Universidad de Chile (BFUC).  
Corpus-based study of amerindian vocabulary in educated Chilean Spanish; primary source for several Quechua and Aymara etymologies in this archive.

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

| # | Term | Origin | Entry type | Etymology status |
|---|------|--------|------------|-----------------|
| 1 | Piñén | Mapudungún | Lexical borrowing | verified |
| 2 | Puma | Mapudungún | Lexical borrowing (global) | unverified |
| 3 | Cahuín | Mapudungún | Borrowing + semantic shift | verified |
| 4 | Ñuñoa | Mapudungún | Toponym | verified |
| 5 | Luche | Mapudungún / Quechua (disputed) | Polysemous term | disputed |
| 6 | Cochayuyo | Quechua | Borrowing via coastal culture | partially verified |
| 7 | Pololo / Polola | Mapudungún | Radical semantic shift | verified |
| 8 | Guata / Wata | Mapudungún | Borrowing with morphological productivity | verified |
| 9 | Poto | Mapudungún | Borrowing with wide semantic range | verified |
| 10 | Guagua | Quechua | Lexical borrowing | verified |
| 11 | Charqui | Quechua | Lexical borrowing | verified |
| 12 | Chuchoca | Quechua / Mapudungún (disputed) | Lexical borrowing | disputed |
| 13 | Mote | Quechua / Mapudungún | Polysemous term | verified |
| 14 | Ñachi | Quechua probable (via Mapuche) | Lexical borrowing | unverified |
| 15 | Ruca | Mapudungún | Borrowing with semantic bifurcation | verified |
| 16 | Huincha / Wincha | Quechua | Lexical borrowing | verified |
| 17 | Chuico | Mapudungún | Lexical borrowing | verified |
| 18 | Pilco | Mapudungún | Lexical borrowing | verified |
| 19 | Choclo | Quechua | Lexical borrowing | verified |
| 20 | Pichintún | Mapudungún + Spanish morphology | Hybrid formation | verified |
| 21 | Poroto | Quechua | Lexical borrowing | verified |
| 22 | Palta | Aymara (via Quechua) | Lexical borrowing | verified |
| 23 | Merkén | Mapudungún (Pehuenche) | Lexical borrowing | verified |
| 24 | Malón | Mapudungún | Generational semantic shift | verified |

---

## Verification methodology

Etymological claims are evaluated against three source types:

1. **Lexicographic** — Primary dictionaries and grammars of Mapudungún, Quechua, and Aymara (Febrés via Lenz, Bertonio 1612 via Lenz, Middendorf via González Retamal, etc.)
2. **Corpus attestation** — Real-use examples in press, recipes, institutional documents, Chilean Spanish corpora, and native speaker testimony (S.A.A.)
3. **Academic** — Peer-reviewed papers and theses for contested or high-stakes etymologies

A claim is `verified` if supported by at least one solid source with explicit method; `disputed` if sources conflict; `unverified` if analytically productive but not yet confirmed in primary sources.

**Unverified ≠ wrong.** Native speaker knowledge is a valid primary source and is labeled as such. The schema separates what is known from what is assumed — which is exactly what most "clean" datasets hide.

---

## Researcher positionality

This archive is curated by a native Chilean Spanish speaker (Santiago, raised primarily by her grandmother, with family roots spanning Puerto Varas, San Fernando, and Santiago). Her background is in Fine Arts Theory and Cultural Management (Universidad de Chile), not formal linguistics. She comes to this work through five years as a Web Search Evaluator, where she observed directly how editorial bias gets encoded as technical criteria in AI systems.

Her native speaker knowledge is treated as a valid primary source and labeled explicitly throughout. She identifies as Hispanic-Chilean (not Mapuche) — a positionality that limits her access to original Mapuche meanings of borrowed words and is documented as a methodological boundary, not erased.

This is not a neutral dataset. No dataset is.

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