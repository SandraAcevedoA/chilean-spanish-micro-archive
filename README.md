# Chilean Spanish Micro-Archive

*English first · [Español más abajo](#español)*

---

## English

**A bilingual annotated lexicon of Chilean Spanish terms with Indigenous substrate:** words from Mapudungún, Quechua and Aymara in which meaning, class coding and colonial history are compressed into everyday speech.

Prototype · 50 entries · EN/ES · curated by Sandra Acevedo A. · browse every entry at [acevedology.com/micro-arch.html](https://acevedology.com/micro-arch.html)

### Why this archive exists

For Sandra Acevedo, language is a cultural artifact. A word like *cahuín*, once a communal Mapuche gathering around a canelo tree and now Chilean slang for gossip, carries the history of the people who used it and of what happened to them. Documenting these words is a form of cultural preservation: it keeps visible the meanings, registers and histories that everyday use and machine translation tend to flatten.

This interest comes from her first field of study, the Theory and History of Art (Universidad de Chile). Her 2006 undergraduate thesis, *Patrimonio, Identidad e Historia*, co-authored with Isabel Ibáñez Figueroa and advised by María Eugenia Brito Astrosa, examined how Chilean cultural institutions mediate public access to heritage. It argued that making heritage formally available without teaching the codes needed to read it reproduces exclusion instead of democratizing access. The same question, who gets access and on whose terms, runs through her work on translation, cultural adaptation and AI, and through this archive.

### What it is

A proof-of-concept dataset for culturally situated NLP evaluation, not a comprehensive dictionary. It is designed to show:

- how culturally situated evaluation data can be structured;
- what is lost when Indigenous-origin vocabulary is processed without cultural context;
- how a responsible dataset handles uncertainty instead of hiding it.

Every entry is bilingual (EN/ES) and carries a **verification-as-claims layer**: etymologies are treated as claims with a status, a method and sources, not as settled facts.

### Why it matters for language technology

Large language models trained mostly on English and standardized Spanish tend to:

- return the surface *chilenismo* meaning without the Indigenous etymology;
- miss the class-coded or historically charged dimensions of common words;
- fail to recognize when a word encodes colonial semantic violence, such as a ritual gathering degraded into "gossip";
- fold distinct Indigenous-origin words into generic "regional variant" labels.

The archive is part of a broader research project on culturally situated NLP for Latin American Spanish: [NLPgap](https://acevedology.com/research.html).

### Contents

| File | What it is |
|---|---|
| [`Data/50chilean-spanish-micro-archive.json`](Data/50chilean-spanish-micro-archive.json) | Structured version: metadata and 50 entries, each with its etymology claims |
| [`Data/50chilean-spanish-micro-archive.csv`](Data/50chilean-spanish-micro-archive.csv) | Flat table: 50 rows, one per term |
| [`SCHEMA.md`](SCHEMA.md) | Field definitions and controlled vocabularies |
| [`SOURCES.md`](SOURCES.md) | Consultation status of each source |
| [`LICENSE`](LICENSE) | CC BY-SA 4.0 legal code |
| [`LICENSE-SCOPE.md`](LICENSE-SCOPE.md) | What the license covers, and what keeps its own status |

### Scope

| | |
|---|---|
| Languages documented | Chilean Spanish, Mapudungún, Quechua, Aymara |
| Entry types | lexical borrowings, semantic shifts, toponyms, polysemous terms, hybrid formations |
| Annotation | bilingual (EN/ES): meaning in use, register, social coding, colonial layer, NLPgap relevance |
| Etymology claims | 51 claims: 38 verified, 9 unverified, 4 disputed |
| Entries | 50 (prototype); target 100+ |
| Primary source for use | native speaker corpus (S.A.A.) |

### The 50 terms

Cahuín · Callampa · Charqui · Charquicán · Chaucha · Chicha · Choclo · Chonchón · Choro · Chuchoca · Chuico · Chuncho · Cochayuyo · Colihue / Coligüe · Copucha · Cototo · Curiche · Guagua · Guarén · Guata / Wata · Huacho / Guacho · Huincha / Wincha · Humita · Laucha · Luche · Malón · Maqui · Merkén · Mote · Nanay · Ñachi · Ñecla · Ñuñoa · Paico · Palta · Pantruca · Paya / Palla · Pichintún · Pilco · Piñén · Pirigüín · Piure · Pololo / Polola · Poncho · Poroto · Poto · Puma · Raulí · Ruca · Trutruca

Each term, with all its fields and claims, can be read at [acevedology.com/micro-arch.html](https://acevedology.com/micro-arch.html).

### How claims are verified

Etymological claims are checked against three kinds of source:

1. **Lexicographic:** dictionaries and grammars of Mapudungún, Quechua and Aymara (Febrés via Lenz, Bertonio 1612 via Lenz, Middendorf via González Retamal, among others).
2. **Corpus attestation:** real use in press, recipes, institutional documents, Chilean Spanish corpora and native speaker testimony (S.A.A.).
3. **Academic:** peer-reviewed papers and theses, for contested or high-stakes etymologies.

A claim is `verified` when at least one solid source supports it with an explicit method; `disputed` when sources conflict; `unverified` when it is analytically productive but not yet confirmed in primary sources.

**Unverified does not mean wrong.** Native speaker knowledge is a valid primary source and is labeled as such. The schema separates what is known from what is assumed, which is exactly what most "clean" datasets hide.

### Sources

All three primary sources are held at the Biblioteca Nacional de Chile, digitized and in the public domain through [Memoria Chilena](https://www.memoriachilena.gob.cl).

- **Lenz, Rodolfo (1910).** *Diccionario etimológico de las voces chilenas derivadas de lenguas indígenas americanas.* Santiago: Universidad de Chile / Imprenta Universitaria. BN MC0038306. [Memoria Chilena](https://www.memoriachilena.gob.cl/602/w3-article-8193.html). The foundational etymological dictionary of Indigenous borrowings in Chilean Spanish, and the main verification source for Mapudungún and Quechua etymologies.
- **Manquilef, Manuel (1911).** *Comentarios del pueblo araucano (La faz social).* Santiago: Imprenta Cervantes. *Anales de la Universidad de Chile*, vol. CXXVIII. BN MC0008915. [Memoria Chilena](https://www.memoriachilena.gob.cl/602/w3-article-8192.html). The first scientific work by a Mapuche author published in the *Anales*; used for Mapuche social practices, material culture and a word list of borrowings from Mapudungún.
- **Valdivia, Luis de (1684).** *Arte y gramática general de la lengua que corre en todo el Reyno de Chile: con un vocabulario, y confesionario.* Sevilla: Thomás López de Haro. BN MC0013038. [Memoria Chilena](https://www.memoriachilena.gob.cl/602/w3-article-8485.html). The earliest colonial grammar of Mapudungún, consulted mainly as negative evidence: what it does not record matters as much as what it does.

Secondary sources:

- **González Retamal, Cristián (2018).** *Vitalidad y mortandad léxica de los mapuchismos.* Universidad de Chile. Lexical vitality of Mapuche borrowings in Chilean Spanish, with recognition data across two age groups (20–50 and 50–80) in two communities.
- **Valencia Alba, Alba (1977).** Voces amerindias en el español culto oral de Santiago de Chile. *Boletín de Filología*, Universidad de Chile. Corpus study of Amerindian vocabulary in educated Chilean Spanish; source for several Quechua and Aymara etymologies.

The consultation status of every source, including the ones still pending, is in [`SOURCES.md`](SOURCES.md).

### Positionality

The archive is curated by a native speaker of Chilean Spanish, from Santiago, raised mainly by her grandmother, with family roots in Puerto Varas, San Fernando and Santiago. Her background is in the Theory and History of Art and in Cultural Management (Universidad de Chile), not in formal linguistics. She comes to this work through five years as a Web Search Evaluator, where she saw directly how editorial bias gets encoded as technical criteria in AI systems.

Her native speaker knowledge is treated as a valid primary source and labeled explicitly throughout. She identifies as Hispanic-Chilean, not Mapuche: a position that limits her access to the original Mapuche meanings of borrowed words, and that is documented as a methodological boundary instead of being erased.

This is not a neutral dataset. No dataset is.

### How to cite

```
Acevedo Alvarado, Sandra D. (2025–). Chilean Spanish Micro-Archive:
A bilingual annotated lexicon with indigenous substrate.
Prototype dataset. acevedology.com.
https://gitlab.com/acevedos/chilean-spanish-micro-archive
```

### License and contact

Sandra Acevedo's original work here (the curation, the annotations, the verification-as-claims layer, the native speaker testimony, the schema and the documentation) is licensed under [Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](LICENSE). Public-domain sources stay in the public domain, third-party works keep their own terms, and the words themselves belong to their languages and communities: the license covers the documentation of those words, not the words. The exact scope is in [`LICENSE-SCOPE.md`](LICENSE-SCOPE.md).

Sandra D. Acevedo Alvarado · Independent researcher · Culturally situated AI systems · [acevedology.com](https://acevedology.com) · [contact](https://acevedology.com/contact.html)

---

## Español

**Un léxico anotado y bilingüe de términos del español chileno con sustrato indígena:** palabras del mapudungún, el quechua y el aimara en las que el significado, la codificación de clase y la historia colonial quedan comprimidos en el habla cotidiana.

Prototipo · 50 entradas · EN/ES · curaduría de Sandra Acevedo A. · todas las entradas se pueden recorrer en [acevedology.com/micro-arch.html](https://acevedology.com/micro-arch.html)

### Por qué existe este archivo

Para Sandra Acevedo, la lengua es un artefacto cultural. Una palabra como *cahuín*, que fue una reunión comunitaria mapuche en torno a un canelo y hoy es la palabra chilena para el chisme, carga la historia de quienes la usaron y de lo que les pasó. Documentar estas palabras es una forma de preservación cultural: mantiene visibles los significados, los registros y las historias que el uso cotidiano y la traducción automática tienden a aplanar.

Este interés viene de su primera formación, la Teoría e Historia del Arte (Universidad de Chile). Su tesis de pregrado de 2006, *Patrimonio, Identidad e Historia*, en coautoría con Isabel Ibáñez Figueroa y dirigida por María Eugenia Brito Astrosa, examinó cómo las instituciones culturales chilenas median el acceso público al patrimonio. Planteó que poner el patrimonio formalmente a disposición sin enseñar los códigos para leerlo reproduce la exclusión en lugar de democratizar el acceso. La misma pregunta, quién accede y en los términos de quién, atraviesa su trabajo en traducción, adaptación cultural e IA, y atraviesa este archivo.

### Qué es

Un dataset de prueba de concepto para la evaluación de NLP culturalmente situada, no un diccionario exhaustivo. Está pensado para mostrar:

- cómo se pueden estructurar datos de evaluación culturalmente situados;
- qué se pierde cuando el vocabulario de origen indígena se procesa sin contexto cultural;
- cómo un dataset responsable maneja la incertidumbre en lugar de esconderla.

Cada entrada es bilingüe (EN/ES) y tiene una **capa de verificación por afirmaciones**: las etimologías se tratan como afirmaciones con un estado, un método y fuentes, no como hechos cerrados.

### Por qué importa para la tecnología del lenguaje

Los modelos de lenguaje entrenados sobre todo en inglés y en español estandarizado tienden a:

- devolver el significado superficial del chilenismo sin la etimología indígena;
- pasar por alto las dimensiones de clase o la carga histórica de palabras comunes;
- no reconocer cuándo una palabra codifica violencia semántica colonial, como una reunión ritual degradada a «chisme»;
- agrupar palabras indígenas distintas bajo etiquetas genéricas de «variante regional».

El archivo es parte de un proyecto de investigación más amplio sobre NLP culturalmente situado para el español latinoamericano: [NLPgap](https://acevedology.com/research.html).

### Contenido

| Archivo | Qué es |
|---|---|
| [`Data/50chilean-spanish-micro-archive.json`](Data/50chilean-spanish-micro-archive.json) | Versión estructurada: metadatos y 50 entradas, cada una con sus afirmaciones etimológicas |
| [`Data/50chilean-spanish-micro-archive.csv`](Data/50chilean-spanish-micro-archive.csv) | Tabla plana: 50 filas, una por término |
| [`SCHEMA.md`](SCHEMA.md) | Definición de los campos y vocabularios controlados |
| [`SOURCES.md`](SOURCES.md) | Estado de consulta de cada fuente |
| [`LICENSE`](LICENSE) | Texto legal de CC BY-SA 4.0 |
| [`LICENSE-SCOPE.md`](LICENSE-SCOPE.md) | Qué cubre la licencia y qué conserva su propio estado |

### Alcance

| | |
|---|---|
| Lenguas documentadas | español chileno, mapudungún, quechua, aimara |
| Tipos de entrada | préstamos léxicos, desplazamientos semánticos, topónimos, términos polisémicos, formaciones híbridas |
| Anotación | bilingüe (EN/ES): significado en uso, registro, codificación social, capa colonial, relevancia para NLPgap |
| Afirmaciones etimológicas | 51 afirmaciones: 38 verificadas, 9 sin verificar, 4 en disputa |
| Entradas | 50 (prototipo); meta: más de 100 |
| Fuente principal de uso | corpus de hablante nativa (S.A.A.) |

### Los 50 términos

Cahuín · Callampa · Charqui · Charquicán · Chaucha · Chicha · Choclo · Chonchón · Choro · Chuchoca · Chuico · Chuncho · Cochayuyo · Colihue / Coligüe · Copucha · Cototo · Curiche · Guagua · Guarén · Guata / Wata · Huacho / Guacho · Huincha / Wincha · Humita · Laucha · Luche · Malón · Maqui · Merkén · Mote · Nanay · Ñachi · Ñecla · Ñuñoa · Paico · Palta · Pantruca · Paya / Palla · Pichintún · Pilco · Piñén · Pirigüín · Piure · Pololo / Polola · Poncho · Poroto · Poto · Puma · Raulí · Ruca · Trutruca

Cada término, con todos sus campos y afirmaciones, se puede leer en [acevedology.com/micro-arch.html](https://acevedology.com/micro-arch.html).

### Cómo se verifican las afirmaciones

Las afirmaciones etimológicas se contrastan con tres tipos de fuente:

1. **Lexicográficas:** diccionarios y gramáticas del mapudungún, el quechua y el aimara (Febrés vía Lenz, Bertonio 1612 vía Lenz, Middendorf vía González Retamal, entre otros).
2. **Atestación en corpus:** uso real en prensa, recetas, documentos institucionales, corpus del español chileno y testimonio de hablante nativa (S.A.A.).
3. **Académicas:** artículos revisados por pares y tesis, para etimologías en disputa o de alto riesgo.

Una afirmación está `verified` (verificada) cuando al menos una fuente sólida la respalda con un método explícito; `disputed` (en disputa) cuando las fuentes se contradicen; `unverified` (sin verificar) cuando es analíticamente productiva pero todavía no se confirma en fuentes primarias.

**Sin verificar no significa equivocada.** El conocimiento de hablante nativa es una fuente primaria válida y se rotula como tal. El esquema separa lo que se sabe de lo que se supone, que es justamente lo que la mayoría de los datasets «limpios» esconde.

### Fuentes

Las tres fuentes primarias están en la Biblioteca Nacional de Chile, digitalizadas y en dominio público a través de [Memoria Chilena](https://www.memoriachilena.gob.cl).

- **Lenz, Rodolfo (1910).** *Diccionario etimológico de las voces chilenas derivadas de lenguas indígenas americanas.* Santiago: Universidad de Chile / Imprenta Universitaria. BN MC0038306. [Memoria Chilena](https://www.memoriachilena.gob.cl/602/w3-article-8193.html). El diccionario etimológico fundacional de los préstamos indígenas del español chileno, y la principal fuente de verificación para las etimologías del mapudungún y el quechua.
- **Manquilef, Manuel (1911).** *Comentarios del pueblo araucano (La faz social).* Santiago: Imprenta Cervantes. *Anales de la Universidad de Chile*, tomo CXXVIII. BN MC0008915. [Memoria Chilena](https://www.memoriachilena.gob.cl/602/w3-article-8192.html). La primera obra científica de un autor mapuche publicada en los *Anales*; se usa para prácticas sociales mapuche, cultura material y una lista de préstamos del mapudungún.
- **Valdivia, Luis de (1684).** *Arte y gramática general de la lengua que corre en todo el Reyno de Chile: con un vocabulario, y confesionario.* Sevilla: Thomás López de Haro. BN MC0013038. [Memoria Chilena](https://www.memoriachilena.gob.cl/602/w3-article-8485.html). La gramática colonial más antigua del mapudungún, consultada sobre todo como evidencia negativa: lo que no registra importa tanto como lo que sí.

Fuentes secundarias:

- **González Retamal, Cristián (2018).** *Vitalidad y mortandad léxica de los mapuchismos.* Universidad de Chile. Vitalidad léxica de los préstamos mapuche en el español chileno, con datos de reconocimiento en dos grupos de edad (20–50 y 50–80) en dos comunidades.
- **Valencia Alba, Alba (1977).** Voces amerindias en el español culto oral de Santiago de Chile. *Boletín de Filología*, Universidad de Chile. Estudio de corpus del vocabulario amerindio en el español culto de Chile; fuente de varias etimologías quechuas y aimaras.

El estado de consulta de cada fuente, incluidas las que siguen pendientes, está en [`SOURCES.md`](SOURCES.md).

### Posicionalidad

El archivo lo cura una hablante nativa del español chileno, de Santiago, criada principalmente por su abuela, con raíces familiares en Puerto Varas, San Fernando y Santiago. Su formación es en Teoría e Historia del Arte y en Gestión Cultural (Universidad de Chile), no en lingüística formal. Llega a este trabajo después de cinco años como evaluadora de búsquedas web (Web Search Evaluator), donde vio de cerca cómo el sesgo editorial se codifica como criterio técnico en los sistemas de IA.

Su conocimiento de hablante nativa se trata como fuente primaria válida y se rotula explícitamente en todo el archivo. Se identifica como hispano-chilena, no mapuche: una posición que limita su acceso a los significados mapuche originales de las palabras prestadas, y que se documenta como un límite metodológico en lugar de borrarse.

Este no es un dataset neutral. Ningún dataset lo es.

### Cómo citar

```
Acevedo Alvarado, Sandra D. (2025–). Chilean Spanish Micro-Archive:
A bilingual annotated lexicon with indigenous substrate.
Prototype dataset. acevedology.com.
https://gitlab.com/acevedos/chilean-spanish-micro-archive
```

### Licencia y contacto

El trabajo original de Sandra Acevedo en este repositorio (la curaduría, las anotaciones, la capa de verificación por afirmaciones, el testimonio de hablante nativa, el esquema y la documentación) se publica bajo licencia [Creative Commons Atribución-CompartirIgual 4.0 Internacional (CC BY-SA 4.0)](LICENSE). Las fuentes de dominio público siguen en el dominio público, las obras de terceros conservan sus propios términos, y las palabras mismas pertenecen a sus lenguas y comunidades: la licencia cubre la documentación de esas palabras, no las palabras. El alcance exacto está en [`LICENSE-SCOPE.md`](LICENSE-SCOPE.md).

Sandra D. Acevedo Alvarado · Investigadora independiente · Sistemas de IA culturalmente situados · [acevedology.com](https://acevedology.com) · [contacto](https://acevedology.com/contact.html)
