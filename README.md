# Chilean Spanish Micro-Archive
### *A bilingual annotated lexicon of Chilean Spanish terms with indigenous substrate*

**Status:** Prototype · 50 entries · active development  
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
| Current entries | 50 (prototype) |
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
│   ├── chilean-spanish-micro-archive.csv    ← flat tabular format (50 entries)
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
| 1 | Cahuín | Mapudungún → Chilean Spanish | Préstamo léxico con desplazamiento semántico en el español chileno | verified |
| 2 | Callampa | Quechua → Chilean Spanish | Préstamo del quechua con tres capas semánticamente distintas en el español chileno: botánica, sociourbanа y vulgar/popular | verified |
| 3 | Charqui | Quechua → Chilean and Andean Spanish | Préstamo léxico del quechua | verified |
| 4 | Charquicán | Mapudungún (compound of Quechua charqui ) → Chilean Spanish | Préstamo compuesto culinario: una palabra quechua para carne seca fue integrada al mapudungún como verbo culinario, luego pasó al español chileno como nombre de un guiso específico | verified |
| 5 | Chaucha | Quechua → Chilean Spanish | Préstamo monetario con estrechez semántica | verified |
| 6 | Chicha | Origin disputed (Antillean / pan-American) → Chilean Spanish | Bebida fermentada con etimología panamericana disputada | disputed |
| 7 | Choclo | Quechua → Chilean and Andean Spanish | Préstamo léxico del quechua | verified |
| 8 | Chonchón | Mapudungún → Chilean Spanish (polysemous) | Préstamo altamente polisémico con al menos cinco sentidos distintos en el español chileno | unverified |
| 9 | Choro | Quechua + multiple possible sources → Chilean Spanish | Término polisémico con sentido primario zoológico (molusco) y múltiples extensiones sociales | unverified |
| 10 | Chuchoca | Quechua / Mapudungún (disputed) → Chilean Spanish | Préstamo léxico que nombra una técnica prehispánica de conservación del maíz; sobrevive en la cocina tradicional rural transmitida a través de la memoria intergeneracional femenina | disputed |
| 11 | Chuico | Mapudungún → Chilean Spanish | Préstamo léxico que nombra un recipiente tradicional; el material pasó del barro al vidrio pero la palabra persiste | verified |
| 12 | Chuncho | Mapudungún → Chilean Spanish | Préstamo zoológico que ha adquirido una rica vida secundaria como marcador cultural e identitario | verified |
| 13 | Cochayuyo | Quechua → Chilean Spanish via coastal culture | Préstamo léxico del quechua al español chileno vía cultura costera mapuche | unverified |
| 14 | Colihue / Coligüe | Mapudungún → Chilean Spanish | Préstamo botánico | verified |
| 15 | Copucha | Mapudungún (+ Quechua/Aymara contamination) → Chilean Spanish | Desplazamiento semántico de lo material a lo social | verified |
| 16 | Cototo | Mapudungún + Quechua contamination → Chilean Spanish | Préstamo con productividad morfológica | unverified |
| 17 | Curiche | Mapudungún → Chilean Spanish | Préstamo racializante: un compuesto mapuche para "persona negra" ( curi = negro + che = gente) fue absorbido al español chileno como término para una persona de piel oscura, funcionando principalmente como intensificador racial con codificación de clase | verified |
| 18 | Guagua | Quechua → Chilean Spanish (also Canarian Spanish, with different meaning) | Préstamo léxico del quechua | verified |
| 19 | Guarén | Mapudungún (probable) → Chilean Spanish | Préstamo zoológico que ocupa una posición específica en la taxonomía popular chilena de roedores | unverified |
| 20 | Guata / Wata | Mapudungún → Chilean Spanish | Préstamo léxico con productividad morfológica | verified |
| 21 | Huacho / Guacho | Quechua wakcha → Chilean and Andean Spanish | Préstamo altamente polisémico del quechua con extensa productividad morfológica | verified |
| 22 | Huincha / Wincha | Quechua → Chilean Spanish | Préstamo léxico del quechua | verified |
| 23 | Humita | Quechua → Chilean and Andean Spanish | Préstamo culinario que nombra una preparación de maíz de origen prehispánico | verified |
| 24 | Laucha | Mapudungún → Chilean Spanish | Préstamo zoológico | verified |
| 25 | Luche | Mapudungún / Quechua (disputed) → Chilean Spanish | Término polisémico | disputed |
| 26 | Malón | Mapudungún → Chilean Spanish | Préstamo léxico con desplazamiento semántico generacional documentado | verified |
| 27 | Maqui | Mapudungún → Chilean Spanish | Préstamo botánico-culinario | verified |
| 28 | Merkén | Mapudungún (Pehuenche) → Chilean Spanish | Préstamo léxico que nombra una preparación de especia pehuenche | verified |
| 29 | Mote | Quechua / Mapudungún → Chilean Spanish | Término polisémico: (1) grano de maíz procesado | verified |
| 30 | Nanay | Quechua → Chilean Spanish | Préstamo afectivo: una palabra quechua para dolor o herida ha sido absorbida al español chileno exclusivamente como palabra-gesto de consuelo | verified |
| 31 | Ñachi | Quechua (probable) → Mapuche → Chilean Spanish | Préstamo léxico que nombra una preparación mapuche tradicional; localizada cultural y geográficamente dentro de Chile | unverified |
| 32 | Ñecla | Origin uncertain (possible Mapudungún) → Chilean Spanish | Préstamo zoológico / lúdico: el nombre del tipo más pequeño y sencillo de volantín en la taxonomía popular chilena | unverified |
| 33 | Ñuñoa | Mapudungún → Santiago toponym | Topónimo | verified |
| 34 | Paico | Quechua → Chilean Spanish | Préstamo botánico-medicinal | verified |
| 35 | Palta | Aymara → Quechua → Chilean Spanish | Préstamo léxico del aimara vía quechua | verified |
| 36 | Pantruca | Mapudungún (probable) → Chilean Spanish | Préstamo culinario que nombra una preparación tradicional de masa cocida en caldo; conservado en uso activo en todas las generaciones a través de transmisión doméstica intergeneracional, principalmente por líneas familiares femeninas | partially verified |
| 37 | Paya / Palla | Quechua pallay → Chilean and Andean Spanish | Préstamo poético-performativo: una palabra quechua para la competencia de verso improvisado es hoy el término primario para la tradición distintiva de poesía oral de Chile | verified |
| 38 | Pichintún | Mapudungún + Spanish morphology (hybrid) | Híbrido morfológico: raíz mapuche pichi (pequeño, poco) + formación con sufijo integrado al español | verified |
| 39 | Pilco | Mapudungún → Chilean Spanish | Préstamo léxico que nombra una variante específica de un plato tradicional | verified |
| 40 | Piñén | Mapudungún → Chilean Spanish | Préstamo léxico incorporado al español chileno | verified |
| 41 | Pirigüín | Mapudungún → Chilean Spanish | Préstamo zoológico que se ha extendido desde su referente literal (renacuajo) para cubrir cualquier ser percibido como embrionario, pequeño o en estado de desarrollo temprano | verified |
| 42 | Piure | Mapudungún → Chilean Spanish | Préstamo zoológico marino | verified |
| 43 | Pololo / Polola | Mapudungún → Chilean Spanish | Préstamo léxico con desplazamiento semántico radical | verified |
| 44 | Poncho | Origin disputed (possibly Mapudungún or Quechua) → Chilean Spanish | Préstamo de vestimenta con rica extensión fraseológica | disputed |
| 45 | Poroto | Quechua → Chilean Spanish | Préstamo léxico | verified |
| 46 | Poto | Mapudungún → Chilean Spanish (origin disputed: also Quechua) | Préstamo léxico con amplio rango semántico y regulación sociolingüística en contextos de infancia | verified |
| 47 | Puma | Mapudungún → global | Préstamo léxico | unverified |
| 48 | Raulí | Mapudungún → Chilean Spanish | Préstamo botánico | verified |
| 49 | Ruca | Mapudungún → Chilean Spanish | Préstamo léxico con bifurcación semántica: (1) vivienda mapuche específica; (2) uso coloquial urbano como descriptor despectivo de espacio desordenado o precario | verified |
| 50 | Trutruca | Mapudungún (onomatopoeic) → Chilean Spanish | Nombre de instrumento onomatopéyico: la palabra mapuche para un gran instrumento de viento hecho de colihue partido, tripa mojada y un cuerno de buey como campana es tanto una descripción del instrumento como una representación fonética del sonido que produce | verified |

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