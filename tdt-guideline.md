# TDT Annotation Guidelines

**Tangut Dependency Treebank (TDT)** — Lotus Sutra and Avataṃsaka Sūtra

Version: 0.1 (working draft)  
Last updated: 2026-10-23

---

## 1. Segmentation and tokenization

Segmentation is decided **first from `LTranslit`, then from character meaning
and context**. Please do not apply a global rule to all multi-character strings.

1. **Keep phonetic transliterations as a single token.** If the syllables of
   `LTranslit` continuously correspond to a Foreign (e.g., Sanskrit) phonetic
   transliteration, and the string is not a semantic calque composed of
   individual character meanings, keep it as one token and retain `OrigLang=sa`.
   Examples: `𘏞𗢈` 菩薩 (Bodhisattva), `𗓚𘄽𗢈` 摩訶薩 (mahāsattva).

3. **Split semantic calques by component.** If each character carries meaning
   and `LTranslit` is not a phonetic rendering of that proper name, split the
   string and assign POS according to context.
   Examples: `𗩴𘔮` 善財 (Sudhana, a calque) → two characters; `𗖰𗚩` 經 /
   sūtra → split; `𗯨𗙏𘝯` 觀世音 → split.

---

## 2. Token fields and MISC

- Each token line has 10 columns in CoNLL-U order:
  `ID FORM LEMMA UPOS XPOS FEATS HEAD DEPREL DEPS MISC`.
- `FORM` is the Tangut Unicode string as transcribed.
- `LEMMA` follows `FORM`.
- `MISC` is project metadata, including `LTranslit`, `Gloss`,
  `OrigLang=sa` which marks Sanskrit-origin transliterations, and
  `CorrectForm` reveals phonological correction.

---

## 3. Multiword expressions and names

- **Phonetic Sanskrit terms that cannot be reliably decomposed by Tangut
  syntax** remain a single token; do not invent internal dependencies.
- **Split semantic compounds** choose the head that explains the whole
  meaning/grammar; other components attach with `compound`, `nmod`, `amod`,
  `obj`, `advmod`, etc. Do not collapse different semantic relations into
  `compound` merely for formal uniformity.
- **Proper name + status/honorific title** (e.g. 觀世音 + 菩薩, person name +
  先生-type structure): this treebank uses **`compound`** as a project
  convention, not `appos`. Existing Lotus `appos` in such structures has been
  changed to `compound`.
- **`appos`** is reserved for genuine apposition/restatement, not for “a title
  after a proper name”.
- **`flat`** is used only for multiword proper names with no analyzable internal
  syntax. If components have been split and are syntactically analyzable,
  annotate their internal syntax. The two former `flat:vv` labels have been
  changed to plain `compound`; new annotations do not use this custom subtype.
- **`fixed`** is used only for genuinely fixed, non-head-modifier multiword
  function expressions, not as a default for general MWEs.

---

## 4. UPOS and contextual rules

| Tag | Rule | Examples / notes |
|---|---|---|
| `PROPN` | Specific persons, places, or individually named entities; components of a split calqued proper name may be `PROPN` in that context | 于闐 `𗘼𘄱`, 實叉難陀 `𗶷𗽇𗓰𗁬`, 善財 `𗩴𘔮`, specific deities/persons such as 毘盧遮那 |
| `NOUN` | Common nouns, doctrinal terms, status categories, group names, generic Buddhist person types | 聲聞 `𗙏𗓁`, 辟支佛 `𘞪𗫨` in a category list → `NOUN`; 菩薩/摩訶薩 as a generic status category → `NOUN` |
| `NUM` | True numerals, quantifiers, or numerical nouns | `𗠝𗗆𗒯` asāṃkhya in an阿僧祇 quantity context → `NUM`; `𘃞𘃞` “one by one” only in that distributive numeral context |
| `ADJ` | Descriptive modifier; do **not** fix a character as `ADJ` merely because a dictionary Gloss is adjectival | Decide from the sentence; do not derive one POS from all historical senses of a character |
| `VERB` | Predicate, or a word still functioning verbally at this treebank's segmentation level | If a calqued term is a multi-character semantic compound, do not change every component to `NOUN` without a defined rule |
| `PART` | Modal, sentence-final, perfective/discourse particles | `𘃞` is usually `PART`; do not globally change it to `NUM`. Use `NUM` only when the context clearly means “one by one” |
| `ADP` | Adposition introducing a noun phrase | Do not treat every character with a dictionary locative sense as `ADP`; decide by syntactic function sentence by sentence |
| `CCONJ` | Coordinating conjunction | Use XPOS `CCONJ`; do not leave the old `CONJ` label |
| `PUNCT` | Punctuation token | Keep `# text` exactly equal to the concatenated token strings |

### Buddhist terminology

- 獨覺/辟支佛 and 聲聞 in contexts such as 「聲聞、辟支佛」 refer to a **class of
  practitioners**; following standard UD, use `NOUN`, not `PROPN` merely because
  the term is Sanskrit-derived. Consider `PROPN` only when a specific named
  individual is meant.
- Deva-class names (阿修羅, 迦樓羅, 乾闥婆, 緊那羅, 摩睺羅伽) in a **category
  list** are `NOUN`; specific mountain names, place names, and individually
  named deities are `PROPN`.

---

## 5. Dependency syntax (UD v2)

- Every sentence has exactly one `root`, whose HEAD is `0`. Every other token's
  HEAD must point to a valid token ID within the same sentence.
- Identify the main predicate/head first, then mark core arguments: `nsubj` for
  subject; `obj` for direct object; `iobj` for indirect object; `xcomp`/`ccomp`
  for required complements; `obl` for non-core locative, temporal, causal, and
  similar constituents. If a marker is present, attach it structurally with
  `case`.
- Noun modifying noun → `nmod`; adjective modifying noun → `amod`;
  determiner → `det`; numeral modifying noun → `nummod`; adverb modifying
  predicate/adjective → `advmod`; conjunction → `cc`, with coordinated items
  as `conj`; punctuation → `punct`.
- Semantic compounds and name + title follow §3. `compound` must express an
  explainable lexical/morphological relation, not serve as a fallback for “I do
  not know which label to use”.
- `HEAD`/`DEPREL` must be decided from each sentence's actual context. Do not
  generate them automatically from POS, token order, or dictionary Gloss alone.
  A tree that passes “single root / valid HEAD / no cycle” is structurally
  valid but not necessarily grammatically correct.
