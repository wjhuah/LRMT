# Annotation Guidelines for Tangut (Under UD-v2)

Date: 2026-10-26. This edition retains the source-review principles and incorporates the decisions on set expansion, discourse particles, nominalization, and agreement. HEAD is a numeric token identifier; DEPREL is the relation label. 

## 1. Sentence Boundaries

### 1.1. Whole propositions

A sentence is normally an independent unit expressing a complete proposition, with at least one subject–predicate structure. Non-predicative expressions may nevertheless form sentences:

- **Titles**, for example, 𘜶𗣼𗾟𗢳𗤻𗵽𗖰𗚩𘐳𗒹𗰗𗒹𗡪。 (大方廣佛華嚴經卷第七十七; The Great and Vast Buddha Avataṃsaka Sūtra, Fascicle 77).
- **Independent interjections or exclamatory expressions**, for example, 𘝶𗦜𘃞。 (何以故？; Why is that?).
- **Fragments**, although this category is not applicable to the Avataṃsaka material. An example can refer to: □□□□，□□□□，□□𗡶𗭍。(聞佛所説，皆大歡喜，信受奉行。), which is in the [Question asked by the Dragon King of the Sea Sāgara-nāgarāja-paripṛcchā](https://www.babelstone.co.uk/Tangut/DragonKing.html).

### 1.2. Sentence-final particle

Some suffix like 𘃞 occurs at the end of a sentence and generally provides a strong signal that a new sentence begins after it, which is very convenient. Some sentences, however, have no overt sentence-final marker. 

### 1.3. The tiling principle ⬜🟦🟧⬜🟦🟧⬜🟦🟧

Copying from another wonderful [Sciptorium](https://copticscriptorium.org/documentation), Tangut sentence segmentation also follows the tiling principle, which contains these two axioms:

1. Every word in the text must belong to a sentence.
2. Sentences must not overlap.

The resulting segmentation must cover the entire text without gaps or overlaps. If material remains between two complete sentences, that material must constitute at least one additional sentence, even if it is not itself a complete syntactic unit.

### 1.4. Punctuation

All Tangut texts **DO NOT** have punctuation. However, for the convenience of sentence segmentation, punctuation marks like "。" and "，" are manually added, which labelled as `Orig=_` in the treebank, where the former is used at the end of a sentence or in the middle of the stanza, while the latter is used at both the 1/4 and 3/4 positions of the stanza; see below.

**Five/seven-character poetry follows its original form.** For texts already with de facto divisions, such as Buddhist stanzas consisting of four five/seven-character lines, we adopt the established one considered as the sentence unit: one 20-character stanza per sentence, which is straightforward.

For example:

> 𗧓𗟦𘞐𘔼𗌭，𗱕𘟀𗣓𗐵𗧓。𗋕𘜶𗣼𗖻𗗙，𗉮𘃛𘊐𗐵𗧓。
> 
> Translation: 我以文殊故，見諸難見者；彼大功德尊，願速還瞻覲。
> 
> Translation: It is because of Mañjuśrī that I have seen all of these who are so rarely seen. May I swiftly return to gaze up at and have audiences with that venerable one of such great meritorious qualities.

**Translation punctuation does not determine Tangut sentence boundaries.** Full stops and question marks in English or Chinese translations must not be used to establish boundaries in the Tangut text.

For example:

> 𗍳𗋕𘋩𘋢𗥤𘋢𗥤𗗙𘝦𗭍𗡶𘋢𗥤𗵘𗹢𗡶𘋢𗥤𗬩𗫦𗡶𘋢𗥤𗤶𗑗𗡶𘋢𗥤𘓞𗄈𗡶𘋢𗥤𗵘𘑨𗭪𘛇𗄭𗡶𘋢𗥤𗗙𗫻𘏚𗼻𘂤𘃽𗡶𘋢𗥤𗗙𘏞𗓽𗕥𘏋𗡶𘋢𗥤𗗙𘎳𗤋𘒮𘜘𗡶𘋢𗥤𗗙𗣼𘉐𗹙𘓳𗡶𘋢𗥤𗩴𗄻𗹬𗗙𘒇𗡶𗤄𗶷𗦇。
> 
> Translation: 汝詣彼問：菩薩云何行菩薩行？云何修菩薩道？云何學菩薩戒？云何淨菩薩心？云何發菩薩願？云何集菩薩助道具？云何入菩薩所住地？云何滿菩薩波羅蜜？云何獲菩薩無生忍？云何具菩薩功德法？云何事菩薩善知識？
> 
> Translation: You should go there, pay your respects, and ask him with regard to the bodhisattva: How he should practice the bodhisattva practices; How he should cultivate the bodhisattva path; How he should train in the bodhisattva precepts; How he should purify the bodhisattva’s resolve; How he should make the bodhisattva vows; How he should accumulate the bodhisattva’s provisions for the path; How he should enter the grounds on which the bodhisattva dwells; How he should fulfill the bodhisattva’s pāramitās; How he should acquire the bodhisattva’s unproduced-dharmas patience; How he should perfect the dharmas of the bodhisattva’s meritorious qualities; and How he should serve the bodhisattva’s good spiritual guides.

We punctuate Tangut texts according to the grammatical criteria. Coordinated structures that share a modifier must remain in the same sentence; otherwise, the shared modifier would lose its attachment site. Translations may be consulted only when grammatically permits more than one segmentation and evidence alone cannot resolve the choice. **Grammatical criteria take priority**; see below.

### 1.5. Space

According to the original manuscript; see image below, certain spaces function as sentence boundaries. Therefore, for any token not followed by such a boundary, we marked its `MISC` with `SpaceAfter=No`.

<img width="800" height="263" alt="image" src="https://github.com/user-attachments/assets/0e4004bf-af22-4043-a8bd-116e08f07cbe" />


### 1.6. Very long sentence

- **25 normalized words or fewer:** follow the syntactic criteria strictly; do not split the unit.
- **More than 25 and up to 55 words:** allow editorial discretion over whether to split.
- **More than 55 words:** normally split at an independent predicate-unit boundary. Retain only an explicitly documented grammatical exception under Section 11; do not separate a shared argument list from its sole predicate.

A typical very long sentence consists of a sequence of subordinate clauses. Although it may grammatically constitute a single sentence, such a unit is difficult to use. Split it at clause boundaries, then return to the regular segmentation criteria as soon as possible.

## 2. Philological Evidence

We preserve the actual manuscript Tangut text writing in `FORM`. When an erroneous character is confirmed, record the correction using `CorrectForm=…`, `Typo=Yes`, and the corrected `LEMMA`.

For example:

In Avatamsaka 0338, the text on the original manuscript is 𗏡𗱕𘉍𗭼𗨻， (當作世光明; will become a light for the world) within which token "𗱕" (諸; all, various) is a typo of "𗯨" (世; world). Thus the very line should be annotated as:

> 8	𗱕	𗯨	NOUN	NOUN	Typo=Yes	10	nmod	_	Gloss=world|LTranslit=rur¹|CorrectForm=𗯨|SpaceAfter=No

([Arakawa, 2011](https://tufs.repo.nii.ac.jp/record/2077/files/jaas081006_ful.pdf))

## 3. Clause Structure, Arguments, and Modifiers

We first identify the predicate of each clause, together with its subject, object, goal, location, instrument, and time expression. The subject is labelled `nsubj`, the core object `obj`, and an additional core argument `iobj`. The dependency follows the grammatical relation between the words. A nearby word is not necessarily the head, and the same person may have different roles in different clauses. We use `vocative` for direct address.

A case marker attaches to the head of its noun phrase with `case`. A noun modifying another noun takes `nmod`; a nominal expression modifying a predicate takes `obl` when it is a non-core argument or adjunct. Whether an argument is core depends on the construction; see [UD iobj](https://universaldependencies.org/u/dep/iobj.html) and [UD obl](https://universaldependencies.org/u/dep/obl.html).

## 4. Personal Names and Titles

Personal names often occur with one or more titles in Buddhist texts. We keep the internal structure of the name consistent, while the head of the complete name–title phrase carries its relation to the rest of the sentence.

| Construction | Internal structure | Head of the complete phrase |
|---|---|---|
| A personal name alone, such as Akṣayamati, Avalokiteśvara, Dharanīṃdhara, Sudhana, or Samantabhadra | The first component is `PROPN`; the other `PROPN` components attach directly to it with `flat` | The first name component |
| Personal name + one nominal title | The first name component attaches to the title with `compound`; the other name components keep `flat` to the first component | The title |
| Personal name + bodhisattva + mahāsattva | Name `compound` → bodhisattva; bodhisattva `compound` → mahāsattva | Mahāsattva, the final title |
| Native “being–awakened” expression for bodhisattva | 𘋢 is the `NOUN` head; 𗥤 attaches to it as `VERB/acl` | 𘋢; when another title follows, 𘋢 attaches to that title |
| Maitreya written as one token + title | The `PROPN` token attaches to the following title with `compound` | The final nominal title |

For example:

> 𗉣𗅋𗋃𘋢𗥤 (意–無–盡–生–覺悟; Akṣayamati Bodhisattva).

When these components are numbered 1–5, we annotate them as follows:

- 1 “intent”: `compound` → 4.
- 2 “without” and 3 “exhaustion”: both `flat` → 1.
- 4 “being”: the head of the complete phrase, carrying `nsubj`, `obj`, `iobj`, `obl`, `nmod`, or `root`, as required by the sentence.
- 5 “awakened”: `VERB/acl` → 4.

When the name occurs without a title, component 1 carries the external relation. Components 2 and 3 still attach to it with `flat`. A case marker, quantifier, or modifier applying to the whole name–title phrase attaches to the head of that complete phrase.

We follow the same principle for other identified names and titles, including Śrīsambhava the youth, Śrīmatī the maiden, Śākyamuni Buddha, and Prabhūtaratna Buddha. The compounds meaning “youth” and “maiden” have their head in the final component. In the transparent honorific “World-Honored One”, the component meaning “honored one” is the head. Buddha, god, and dragon can also be common nouns; their part of speech depends on their use in the sentence.

## 5. Distinguishing compound, flat, fixed, conj, and appos

We use a consistent direction for these relations: `compound` points from the earlier component to the later head; `flat`, `fixed`, `conj`, and `appos` have the first component as head. The direction of `compound` is a convention of this project.

A `compound` analysis needs grammatical evidence. Familiar meaning, an idiomatic reading, or inclusion in a dictionary is not sufficient by itself. Conditions, causes, purposes, and coordinated events keep their own clause structure, even when the text is written continuously. Within a name, every `flat` component attaches directly to the first component. We use `fixed` for grammaticalized fixed expressions.

For example, the totality expression 𗄑𗄑 has its head in the first component, with the second attached by `fixed`. Its classification depends on its function:

- `DET/det` when it determines a nominal expression.
- `PRON` when it is an independent argument.
- `ADV/advmod` when it modifies a predicate.

We mark `ExtPos` on the first component to show the category of the whole expression. Both components belong to the same expression and share its scope.

In coordination, each later conjunct attaches directly to the first conjunct at the same level. Nested coordination keeps its own levels. A coordinator takes `cc` to the head of the conjunct it introduces. When a sentence begins with a coordinator continuing the preceding sentence, it attaches to the current clause head. The dependency remains within the current sentence.

We annotate 𘆄 “etc.; others” as `PRON/conj` with `PronType=Ind` in enumerations and expressions meaning a person together with others. It attaches to the first head of the expression being expanded.

For example:

> 𗧓𘆄 (我等; I and others/we): 𘆄 `conj` → 𗧓.

In a list N₁, N₂, etc., both N₂ and 𘆄 attach to N₁. In “such as this, etc.”, 𘆄 expands the preceding demonstrative expression. Equality predicates and repeated expressions meaning “equal” have their own analysis. Our use of `PRON` for 𘆄 is a project convention.

In “gold, silver, etc. treasures”, “treasures” is the head of the complete noun phrase. The first example, “gold”, attaches to it with `nmod`; “silver” and 𘆄 attach to “gold” with `conj`. We use the same structure for expressions such as “gods, dragons, etc. bodies”.

We use `appos` when two complete nominal expressions identify or explain the same referent. A comma is optional.

## 6. Part of Speech

We assign part of speech according to the word's function in its construction. A verbal dictionary meaning can occur in a nominal compound without expressing a separate event. Therefore, the same lemma may have different UPOS tags in different uses.

In this edition, `XPOS` has the same value as `UPOS`.

## 7. Nominalization, Causation, and Negation Scope

We annotate the words present in the text. A nominal predicate can occur without a copula, and several predicates meaning “abode” can form a coordinated structure.

Conditional, causal, and purposive clauses attach with `advcl` to the predicate they modify.

Predicate negation is marked by `PART` or `ADV`, with `advmod` and `Polarity=Neg`. Negative determination within a noun phrase uses `DET/det` with `PronType=Neg`.

The grammaticalized causative 𗟻 attaches to the lexical predicate with `aux`. A lexical causative expressing its own event and taking its own arguments follows the corresponding lexical construction.

## 8. Auxiliaries, Agreement Clitics, and Traditional Prefixes

We attach an auxiliary to the predicate it serves with `aux`. A linking copula attaches to the nonverbal predicate with `cop`. Auxiliary registration records both the lemma and its grammatical use. The local registration proposal remains separate from official registration.

We retain the established segmentation of postverbal person markers as clitic words. Their position in the verb complex, their occurrence alongside lexical arguments, and their lack of an independent argument role help distinguish them from free pronouns. Postverbal 𗧓, 𘉞, and the agreement use of 𗐱 are annotated as `AUX/aux`. We record `Person=1` or `Person=2` where the analysis supports it. The second-person plural agreement uses of 𗐱 in Lotus 0012 also carry `Number=Plur`.

These forms express grammatical agreement. The segmentation applies to the clitic uses identified here; other bound morphemes need their own evidence for separate word status. UD allows an agreement-only `AUX` analysis where the evidence supports this distinction from an independent pronoun; see [UD AUX](https://universaldependencies.org/u/pos/AUX.html).

Free 𗧓 “I/we” is `PRON` and takes its argument or possessive relation. A free pronoun and an agreement clitic may occur together. For example, in the source sequence across Avatamsaka 0411–0412, the first of two adjacent nga forms is postverbal agreement, and the second begins the following sentence as its subject. Agreement may refer to a subject or an object, so a person marker alone does not establish an additional subject; see [Kepping 1994](https://doi.org/10.1017/S0041977X00024903).

𗐱 also has a conditional use. In the two Avatamsaka expressions meaning “if speaking in brief”, we follow Arakawa 2011, note 70, and annotate it as `SCONJ/mark` attached to “speak”.

Some modal, aspectual, optative, and directional forms are separate tokens in this corpus. We use `ADV/advmod` for an independent directional modifier, `AUX/aux` for a grammaticalized tense–aspect–mood–evidentiality (TAME) marker, and `PART/discourse` for a grammatical question particle. The construction determines the category.

For example, interrogative a in Lotus 0024 and directional a before “arise” in Lotus 0084 have different functions. The modal preverb 𗉘 in the former question is `AUX/aux` with `Mood=Pot`. Demonstrative uses of the same character keep their nominal or adnominal analysis. For preverb functions, see [Arakawa 2021](https://journals.eco-vector.com/1811-8062/article/view/77306); for the modal distinction, see [Beaudouin 2023](https://doi.org/10.1075/lali.00142.bea).

We distinguish three uses of 𗭪:

- In V–sji²–N, the verb modifies N with `acl`, and the determinative nominalizer attaches to the verb as `SCONJ/mark`.
- With a finite predicate and a TAME function, sji² attaches to the predicate as `AUX/aux`.
- The homophonous noun meaning “implement” is `NOUN`.

See [Beaudouin 2023](https://doi.org/10.1075/lali.00142.bea) and [Ji 2026](https://doi.org/10.1075/lali.00266.ji). 

## 9. Negation, potentiality, and nominal predicates

We distinguish three kinds of negation:

1. **Predicate negation:** `PART` or `ADV`, attached by `advmod`, normally with `Polarity=Neg`.
2. **Negative nominal determination:** `DET/det`, with `PronType=Neg`.
3. **Negative existence or lack:** lexical 𗤋 as `VERB`, with `Polarity=Neg`; its nominal argument and any subject or possessor follow the construction.

In V–𘏚–𗤋, 𘏚 provides an overt place or nominalizing head. The verb attaches to it with `acl`, and the resulting nominal expression can be the object of the predicate meaning “lack”. This structure needs to be distinguished from an ordinary verb with a location. A negative clause is `ccomp` of a cognition verb when it expresses the content of cognition. A parallel assertion keeps its separate clause relation.

In “there is no not-V”, the inner negator modifies V. The outer negative-existential predicate takes the negative clause as `csubj`. Each negator therefore keeps its own scope. We follow this analysis in Avatamsaka 0247, 0253, and 0261.

In its nominal copular use, negative 𗅔 is `AUX/cop` attached to the nominal predicate. Existential 𗤋 and negative determiners keep their corresponding analyses.

## 10. Causatives, agreement, and nominalization

In the grammaticalized causative construction, 𗟻 attaches as `AUX/aux` to the lexical predicate within its scope. The causer is the subject of the causative clause. An overt causee is `obj` when the lexical predicate is intransitive. When that predicate already has an object, an additional core causee is `iobj`. We annotate the overt participants and leave omitted participants unexpressed.

An adjective may be the predicate of this grammatical causative construction. It keeps `ADJ` even when the causee is represented as `obj`. Lexical causation with a separately headed clause follows its own clause structure; see [UD valency-changing operations](https://universaldependencies.org/u/overview/simple-syntax.html#valency-changing-operations).

Postverbal first-person 𗧓 and second-person 𘉞 follow the `AUX/aux` convention in Section 8. Free pronouns, including those followed by case markers, remain `PRON`. At a clause boundary, we distinguish an agreement form ending one clause from a free pronoun beginning the next. Both have their own grammatical role.

A verbal or adjectival expression can also function as a nominal argument. In multiword expressions with zero nominalization, such as “the extraordinary” and “those difficult to see”, we keep the lexical `ADJ` and mark the phrase head with `ExtPos=NOUN`. A clause serving as the argument of “difficult” takes `csubj`. A clause modifying an overt nominalizer takes `acl`.

A title, body-part expression, or quality expression may refer to its possessor. We record this reading as an editorial interpretation while retaining the words present in the text. In the welcoming sequence, directly addressed nominal epithets take `vocative`; accompanying events keep their clause structure.

## 11. Word boundaries

The totality expressions 𗑷𗄊 and 𗄑𗄑 have the first component as head and the second attached by `fixed`. We use `PRON` for an independent argument and `ADV` for adverbial totality, with the expression's `ExtPos` on the first component. The expression 𗉮𘃛 “immediately” is a lexical adverbial compound: the first component attaches to the second with `compound`. Nominal 𗙼𗙷 “front–front” also has its head in the final component. An adverbial use may have `ADV` as its external category.

A sentence exceeding 55 normalized words requires an explicit boundary decision. We keep a nominal list with its sole following predicate, and preserve shared nominalizers, complement-taking predicates, modals, and discourse expressions whose scope extends over the construction. During source review, the repeated independent copular clauses in Avatamsaka 0210, 0212, 0213, and 0216 were split. Long clause complexes retained as single sentences were recorded separately. We preserve those decisions and complete Tangut stanzas in this edition.

The original and final sentence IDs are mapped. A translation paragraph may cover several Tangut grammatical units. We record that scope in the external parallel-text records. The CoNLL-U headers retain their four comments, and Tangut grammar determines the sentence boundaries.

The two-word comparative postposition 𗋚𗍊 has its head in the first component. We annotate 𗋚 as `ADP/case` attached to the nominal standard of comparison, and 𗍊 as `ADP/fixed` attached to 𗋚. The first component carries `ExtPos=ADP`. Arakawa 2011, note 79, identifies this combined comparative use. Independent directional 𗋚 and independent comparative 𗍊 keep their separate analyses.

In its three occurrences, 𗑟𘎆 “companions/relatives” is a lexical nominal compound. Both components are `NOUN`; the first attaches to the second with `compound`, and the second carries the external relation. Modifiers of the whole phrase attach to that head. The reciprocal dictionary label of the second character does not by itself establish a reciprocal argument in this expression.

We use `ADJ` for a simple property such as “deep” or “shallow”, including when it is predicative. Transitive “increase” or “fulfil”, with an object, is `VERB`. In “difficult to know/enter/do/measure”, the verbal argument of “difficult” takes `csubj`, including when that argument consists of a single token. For sentence and clause particles take `discourse:sp`; other expressive elements take plain `discourse` as specified below.

| Construction | UPOS / DEPREL | Head and scope |
|---|---|---|
| Sentence/clause-final 𘃞 lə¹ | `PART/discourse:sp` | The head of the statement, question, or quotation that it closes |
| Numerical/distributive 𘃞𘃞 “one by one” | `NUM/nummod` for nominal quantity or `ADV/advmod` for distributive use; the first component attaches to the second with `compound` | The nominal being counted or the predicate modified |
| Interrogative a¹ in Lotus 0024 | `PART/discourse` | The predicate of the question |
| Praise interjection 𗹫 and exclamative 𗣀 | `INTJ/discourse` and `PART/discourse`, respectively | The interjection attaches to the relevant predicate; 𗣀 attaches to the interjection. Repeated interjections may take `conj` |
| Enumerative/associative 𘆄 | `PRON/conj`, `PronType=Ind` | The first head of the expression being expanded |
| Finite-predicate TAME sji² | `AUX/aux` | The predicate it modifies |
| Adnominal nominalizing sji² | `SCONJ/mark` | The subordinate verb, which attaches to the overt noun with `acl` |
| Person-indexing clitic | `AUX/aux` | The predicate carrying the agreement |
| Degree, time, or directional adverb | `ADV/advmod` | The predicate or modifier within its scope |
| Nominal case marker / clausal subordinator / coordinator | `ADP/case` / `SCONJ/mark` / `CCONJ/cc` | The nominal head / subordinate predicate / introduced conjunct |

In the Avatamsaka assertion and comparison complexes ending in `PART/discourse:sp` lə¹, we attach the particle to the sentence root. It closes the complete assertion. So, consistency means that the same construction receives the same analysis. 

## 12. Tokenization

We follow these decisions in both treebanks:

| Construction | Word boundaries | Annotation |
|---|---|---|
| An established multi-character transcription of one borrowed word or proper name | Keep the whole form recorded in the inventory. Short and full spellings of Mañjuśrī remain distinct written forms | Give the whole word its contextual UPOS. Its phonographic syllables have no separate syntactic relation |
| A native name with separately analyzed components, such as Sudhana or Akṣayamati | Keep the components separate, following the corpus segmentation | The first component is `PROPN`; the others attach directly to it as `PROPN/flat`. Titles follow Section 4 |
| Name + one or two titles | Keep the name unit and each independently analyzed title separate | The final nominal title carries the external relation; see Section 4 |
| Native 𘋢𗥤 “bodhisattva” | Keep the two lexical units of this transparent nominal expression | 𘋢 is the `NOUN` head; 𗥤 attaches to it as `VERB/acl` |
| Transparent nominal or verbal compounds analyzed as separate lexemes | Keep the lexical units where the grammatical structure supports a compound | The earlier component attaches to the later head with `compound`. Independent events keep their clause relations |
| Noun + case marker, or clause + subordinator | Keep the marker separate from its host phrase | `case` to the nominal head or `mark` to the subordinate predicate; a multiword grammatical marker uses first-headed `fixed` |
| Agreement clitics analyzed as words | Follow the segmentation in Section 8 | `AUX/aux`; free pronouns remain `PRON` with their argument or possessive relation |
| Bound inflection without established syntactic word status | Keep it within the word | Record the supported feature on that word. A separate clitic analysis needs grammatical evidence |
| Sentence/clause-final 𘃞 | Keep it separate from the predicate | `PART/discourse:sp` to the head of the proposition it closes |
| Functional repetition 𗄑𗄑 and totality expression 𗑷𗄊 | Keep two components | The first carries the external relation and `ExtPos`; the second takes `fixed` |
| Numerical/distributive 𘃞𘃞 | Keep both components | The first attaches to the second with `compound`; the expression takes `NUM/nummod` or `ADV/advmod` according to its function |
| Composite written numerals with separate lexical units | Keep each numerical unit | Use the internal numerical hierarchy and `nummod` to the counted nominal. Adjacent numerical units do not by themselves form coordination |
| Punctuation | Keep each punctuation mark as a separate token | `PUNCT/punct` within the same sentence; word boundaries still follow grammatical criteria |

Free arguments, genitives, modifiers, and independently scoped predicates remain separate, including in familiar Buddhist expressions. An established borrowed word keeps its whole form even when several syllabograms are used to write it. Short and full spellings are preserved in `FORM`.

Tangut studies distinguish free pronouns, person markers, preverbs, nominalizers, and postpositions. These distinctions provide evidence for word segmentation. We refer to Kepping for agreement and Beaudouin for verbal and nominal constructions. Gong Xun's [2024 transcription notes](https://homepage.univie.ac.at/xun.gong/tangut/phonology-202409.html) describe enclitics and prosodic groupings. A prosodic grouping may contain several syntactic words. Our treatment of clitics follows the convention stated in Section 8; phonological suffixes still need grammatical evidence for separate tokenization.

## 13. UPOS

`XPOS` has the same value as `UPOS` in this edition. The counts below are those reported for the two files. We classify each occurrence by its grammatical function, so the same character may receive different tags. `SYM` and `X` are unused; their criteria are included for completeness.

| UPOS | Tokens | Function and annotation |
|---|---:|---|
| `ADJ` | 918 | A property word, such as “good”, “large”, or “deep”. It usually takes `amod` and may also be a nonverbal predicate. An adjective can head an `acl`, take a clausal argument with `csubj`, or carry `ExtPos=NOUN` in zero nominalization. It keeps `ADJ` in a grammatical causative |
| `ADP` | 983 | A nominal case marker or postposition, attached to the noun-phrase head with `case`. A second component of a multiword postposition may take `fixed`. Clausal subordinator uses are analyzed separately |
| `ADV` | 970 | A non-clausal modifier of a predicate or another modifier, usually with `advmod`. This includes independent direction, degree, and adverbial totality. An adverb may also be part of a `compound` or `fixed` expression. Agreement markers follow the `AUX` convention |
| `AUX` | 574 | An auxiliary expressing TAME, grammatical causation, or the agreement function described in Section 8. It attaches to the lexical predicate with `aux`; a linking copula takes `cop` to the nonverbal predicate. Lexical uses of “get”, “want”, and “do” are classified by their construction |
| `CCONJ` | 53 | A coordinator linking parallel units. It takes `cc` to the conjunct it introduces, or forms part of a fixed connective. Comitative `ADP` and conditional or causal `SCONJ` uses are distinguished by function |
| `DET` | 959 | A demonstrative, total, indefinite, interrogative, or negative determiner. It takes `det` to its nominal head or forms part of a fixed determiner expression. An independent demonstrative phrase with its own case marker is `PRON` |
| `INTJ` | 5 | An expressive or praise interjection, attached with plain `discourse`. A repeated interjection may take `conj`. A praise statement expressing a complete proposition keeps its clause structure |
| `NOUN` | 4343 | A common noun, religious class term or title, nominalized lexical item, or overt person/place nominalizer serving as head. It takes nominal argument or modifier relations, `compound`, or the relation of a nonverbal predicate. A word with a verbal dictionary gloss may have a nominal use |
| `NUM` | 216 | A definite number or lexical numeral. It takes `nummod` to the counted nominal and follows the numerical hierarchy or compound structure inside a composite number. The indefinite expression “etc.; others” is `PRON` |
| `PART` | 297 | A grammatical particle outside the other function-word classes. Predicate negation takes `advmod`; final 𘃞 takes `discourse:sp`; a preverbal question particle or a word-level exclamative component takes plain `discourse`. Auxiliaries and subordinators keep `AUX` and `SCONJ` |
| `PRON` | 302 | A nominal substitute or independent pronominal argument, carrying its argument or modifier relation. We use `PRON` with `PronType=Ind` and `conj` for 𘆄. Postverbal agreement follows the separate clitic analysis |
| `PROPN` | 344 | An identified proper name. The first component carries the name's external relation, and the other separate name components take `flat`. With a nominal title, the name may attach to it with `compound`. Common religious class terms retain their nominal classification |
| `PUNCT` | 1074 | A punctuation mark, attached to the relevant local head with `punct`. Titles remain lexical expressions, and an uncertain Tangut character still needs a lexical analysis |
| `SCONJ` | 124 | A subordinator or the determinative nominalizer described in Section 8. It takes `mark` to the subordinate predicate. Multiword grammatical subordinators have the first component as head, with the others attached by `fixed` |
| `SYM` | 0 | Unused. This tag is available for a genuine non-punctuation symbol with a linguistic function. Tangut logograms and ordinary punctuation keep their own categories |
| `VERB` | 2697 | A lexical event, action, or existential/negative-existential predicate. It takes predicate or clause relations, `compound` where supported, or `acl` in a transparent nominal expression. Proper names and nominal compounds are analyzed as their complete constructions |
| `X` | 0 | Unused. This tag is available for material outside the ordinary lexical categories under the UD definition. An identifiable Tangut word keeps its lexical analysis even when some aspects remain uncertain |

## 14. Dependency and HEAD

### 14.1. Relations used

The two files use 31 relation labels. The table gives the grammatical criterion, the head, and an example for each. Counts and examples come from the corpus summarized in this edition. The examples show how we apply the annotation rules.

| DEPREL | Tokens | Function | HEAD | Corpus example (dependent → head) |
|---|---:|---|---|---|
| `acl` | 628 | A clause modifying a nominal expression, including the native title component meaning “awakened”. A simple attributive adjective takes `amod` | The overt nominal or nominalized phrase head being modified | avatamsaka_sutra_0003:3 𘃽 → 𘄿 |
| `advcl` | 458 | A conditional, causal, purposive, temporal, manner, or background clause. Its predicate may be nonverbal | The predicate whose event or proposition the clause modifies | avatamsaka_sutra_0004:10 𗶷 → 𘘣 |
| `advmod` | 1089 | A non-clausal adverbial modifier of degree, time, direction, or another adverbial function; also the predicate negators described above | The predicate or modifier within its scope. Agreement and nominalization follow their own relations | avatamsaka_sutra_0004:8 𘚔 → 𗶷 |
| `amod` | 723 | An adjectival attribute, including one with a degree modifier | The nominal it characterizes. Predicative adjectives follow their clause relation | avatamsaka_sutra_0001:1 𘜶 → 𗣼 |
| `appos` | 16 | A complete nominal expression identifying or explaining the same referent as another nominal expression | The first co-referential nominal head. A comma is optional; a simple attributive quality takes `nmod` or `amod` | avatamsaka_sutra_0024:15 𘋟 → 𗦻 |
| `aux` | 478 | A grammatical TAME, causative, or agreement element under the analyses in Sections 8 and 10 | The lexical predicate, including an adjective in a grammatical causative. Agreement does not add a free argument | avatamsaka_sutra_0007:10 𗧓 → 𘃡 |
| `case` | 954 | A nominal case marker or postposition, including the first component of a multiword postposition | The head of the complete nominal phrase marked | avatamsaka_sutra_0003:9 𗗙 → 𗢭 |
| `cc` | 50 | A coordinator introducing a parallel unit or continuing coordination from the preceding sentence | The introduced conjunct's head; for sentence-initial continuation, the current clause root | avatamsaka_sutra_0027:12 𗅉 → 𗚉 |
| `ccomp` | 64 | A selected content clause whose subject is independently licensed. The content predicate may be nonverbal | The speech, cognition, demonstration, or other predicate selecting the clause | avatamsaka_sutra_0006:8 𗫦 → 𗄻 |
| `compound` | 1265 | A nominal, verbal, or adverbial compound supported by its grammatical structure | The later lexical head. Independent arguments, events, and grammatical fixed expressions keep their respective relations | avatamsaka_sutra_0001:7 𗖰 → 𗚩 |
| `conj` | 1035 | A later parallel nominal, modifier, predicate, clause, or the set-expander 𘆄 | The first conjunct at the same level. Nested coordination keeps its levels; 𘆄 attaches to the expression it expands | avatamsaka_sutra_0004:25 𗕪 → 𘞁 |
| `cop` | 96 | A linking copula, including the negative nominal copula described in Section 9 | The nonverbal predicate. Lexical existence and becoming keep their lexical analysis | avatamsaka_sutra_0129:8 𘟂 → 𘛇 |
| `csubj` | 11 | A verbal or clausal subject, including in “difficult to know/enter” | The predicate taking the clause as its subject. A nominal subject takes `nsubj` | avatamsaka_sutra_0056:45 𗄻 → 𗣓 |
| `det` | 707 | An adnominal demonstrative or quantificational determiner, including negative determination | The nominal it determines. An independent pronoun with its own case marker follows its argument relation | avatamsaka_sutra_0004:1 𗉘 → 𘝨 |
| `discourse` | 10 | An interjection, word-level exclamative component, or preverbal question particle | The local expressive host or the predicate within its scope. Final 𘃞 takes `discourse:sp` | avatamsaka_sutra_0371:19 𗹫 → 𗖼 |
| `discourse:sp` | 106 | Sentence/clause-final `PART` 𘃞. Numerical and distributive uses are analyzed separately | The head of the assertion it closes: the sentence root for the complete assertion, or the local predicate of an internal proposition or quotation | avatamsaka_sutra_0010:20 𘃞 → 𗫻 |
| `fixed` | 313 | A non-head component of a grammatical fixed expression | The first component of the same expression, directly | avatamsaka_sutra_0010:12 𗄑 → 𗄑 |
| `flat` | 178 | A separate `PROPN` component within a native personal name without an internal dependency analysis | The first `PROPN` of that name, directly. A following title has its separate relation to the name | avatamsaka_sutra_0004:4 𘔮 → 𗩴 |
| `iobj` | 46 | An additional core nominal argument, including a core causee when the causative's lexical predicate already has an object | The predicate taking that core argument. Spatial and instrumental uses are distinguished by their construction | avatamsaka_sutra_0007:5 𗧓 → 𘎪 |
| `mark` | 123 | A clausal subordinator or adnominal determinative sji | The subordinate lexical predicate | avatamsaka_sutra_0027:23 𘔼 → 𗒐 |
| `nmod` | 1286 | A nominal modifier or possessor of another nominal expression, including a nominalized phrase | The nominal head modified. A non-core nominal dependent of a lexical predicate takes `obl` | avatamsaka_sutra_0001:2 𗣼 → 𗚩 |
| `nsubj` | 414 | An overt nominal or pronominal subject, including the subject of a nonverbal assertion | Its local predicate. Agreement clitics, addressees, and named participants follow their grammatical function | avatamsaka_sutra_0002:5 𗶷𗽇𗓰𗁬 → 𗯝 |
| `nsubj:pass` | 1 | The promoted subject in the passive/affected construction found in this corpus | The lexical passive/affected predicate. This subtype is proposed for txg, with the analysis based on the Tangut construction | lotus_sutra_0067:7 𗭒 → 𘐏 |
| `nummod` | 203 | A lexical number or numerical quantity | The counted nominal, or a higher numerical unit within a composite numeral. Indefinite “others” follows its pronominal analysis | avatamsaka_sutra_0001:12 𗒹 → 𘐳 |
| `obj` | 1125 | A core theme or affected nominal, nominal naming content, or the causee of an intransitive grammatical causative | The lexical predicate taking the object. Subjects, additional core arguments, and instrumental/spatial obliques keep their own relations | avatamsaka_sutra_0003:2 𗐯 → 𘃽 |
| `obl` | 664 | A non-core nominal argument or adjunct, including spatial, temporal, instrumental, comparative, and comitative expressions | The predicate modified. A nominal modifying another noun takes `nmod` | avatamsaka_sutra_0002:1 𗁬 → 𗯝 |
| `parataxis` | 101 | A loosely joined independent assertion, question, reporting/quoted unit, or another independently headed proposition | The main or first relevant independent predicate in the sentence. Adnominal and selected content clauses keep their clause relations | avatamsaka_sutra_0141:68 𗨄 → 𘀽 |
| `punct` | 1074 | A punctuation mark | The relevant local syntactic unit within the same sentence | avatamsaka_sutra_0001:14 。 → 𘐳 |
| `root` | 503 | The main lexical or nonverbal predicate, or the nominal head of an independent title | 0. Each sentence has one root, selected by its grammatical structure | avatamsaka_sutra_0001:9 𘐳 → 0 |
| `vocative` | 51 | A directly addressed person, title, or nominal epithet | The predicate of the utterance containing the address. Narrative subjects and recipients follow their argument roles | avatamsaka_sutra_0005:2 𗇋 → 𗛈 |
| `xcomp` | 87 | A selected open predicative complement, including a controlled action or a predicative naming result | The selecting predicate. An independently subject-bearing content clause takes `ccomp`; an adjunct takes `advcl` | avatamsaka_sutra_0007:8 𘎪 → 𘃡 |

### 14.2. Relations not used

The following eight universal base relations are unused in these files. They remain available when a future example meets the relevant criterion.

| Unused relation | Function | HEAD |
|---|---|---|
| `clf` | A syntactic numeral classifier supported by the language-specific analysis. Measure nouns need their own classification | The associated nominal head |
| `dep` | A dependency for which a more specific analysis cannot be established. The uncertainty is recorded externally | The best-supported local content head |
| `dislocated` | A peripheral topic outside the clause's ordinary argument structure, often resumed within the clause. Distance alone does not establish dislocation | The clause predicate |
| `expl` | An expletive or clitic-doubling construction without an ordinary argument contribution. The agreement-only `AUX` convention does not itself establish an expletive | The predicate taking the expletive |
| `goeswith` | A word accidentally split in the source under UD's erroneous-spacing analysis. The lexical units and clitics kept separate in this corpus have their own word status | The first part |
| `list` | A list without an ordinary syntactic relationship between its items. Coordinated Buddhist enumerations take `conj` | The first list head |
| `orphan` | A remnant of an omitted predicate under UD's promotion analysis. The basic tree uses the overt remnants | The promoted remnant in the same clause |
| `reparandum` | An abandoned expression followed by a repair in a correction or disfluency. Confirmed character errors follow the FORM/LEMMA/CorrectForm/Typo convention | The head of the repair |

## 15. Feature and Gloss

We record features supported by the grammatical analysis of each occurrence. A TAME function described in auxiliary registration does not automatically require a FEATS value on every use. The feature/value/UPOS combinations below are included in the separate proposed txg registration.

| Feature | Attested values | Use |
|---|---|---|
| `ExtPos` | `ADP`, `ADV`, `CCONJ`, `DET`, `NOUN`, `PRON`, `SCONJ` | The external category of a multiword functional expression or a nominalized expression. We mark it on the head of the expression |
| `Mood` | `Pot` | The potential modal construction identified in this edition. Other auxiliary functions receive features only where the particular analysis supports them |
| `Number` | `Plur` | The plural agreement use described above. A dictionary gloss “I/we” leaves the number of an individual free-pronoun occurrence to be established from its construction |
| `Person` | `1`, `2` | The person expressed by a separately analyzed agreement element. Its subject or object reference is determined from the clause |
| `Polarity` | `Neg` | Predicate negation, negative existence, or the negative copular construction, with the scope identified for each occurrence. Negative nominal determination takes `PronType=Neg` |
| `PronType` | `Dem`, `Ind`, `Int`, `Neg`, `Prs`, `Tot` | `Prs` for free personal pronouns; `Dem` for demonstratives; `Tot` for totality; `Ind` for indefinite determination and pronominal set expansion; `Neg` for negative nominal determination; `Int` for interrogative uses. Proper names follow their own analysis even when the same character has a pronominal use elsewhere |
| `Reflex` | `Yes` | A nominal reflexive use identified in the text. An adverb meaning “self/by oneself” requires its own analysis |
| `Typo` | `Yes` | A confirmed source-character error, accompanied by `CorrectForm` and the corrected `LEMMA`. We preserve `FORM` |

## References

- Arakawa, Shintarō. 2011. *An Annotated Japanese Translation of the Tangut Version of Avataṃsaka Sūtra vol. 77 in Princeton University Collection*. Journal of Asian and African Studies 81:147–305. [Institutional original](https://tufs.repo.nii.ac.jp/record/2077/files/jaas081006_ful.pdf).
- Arakawa, Shintarō. 2021. *On the Tangut Prefix 2da:-*. Pis'mennye pamiatniki Vostoka 18(3):64–73. [DOI](https://doi.org/10.17816/WMO77306).
- Beaudouin, Mathieu. 2023. *Tangut and Horpa languages: Some shared morphosyntactic features*. Language and Linguistics 24(4):611–673. [DOI](https://doi.org/10.1075/lali.00142.bea).
- Chen, Bingying. 1985. Tujieben Xixiawen Guanyinjing yishi, Dunhuang Research 1985(3):49–58. 
- Coptic Scriptorium: [Documentation](https://copticscriptorium.org/documentation)
- Gong, Xun. 2024. [GX202409 transcription notes](https://homepage.univie.ac.at/xun.gong/tangut/phonology-202409.html).
- Ji, Yue. 2026. *The sigmatic perfect 𗭪 sji² in Tangut and its grammaticalization*. Language and Linguistics 27(4):710–734. [DOI](https://doi.org/10.1075/lali.00266.ji).
- Kepping, Ksenia B. 1994. *The conjugation of the Tangut verb*. Bulletin of SOAS 57(2):339–346. [DOI](https://doi.org/10.1017/S0041977X00024903). Agreement evidence is distinct from the present UD tokenization decision.
- Universal Dependencies: [tokenization](https://universaldependencies.org/u/overview/tokenization.html), [compound](https://universaldependencies.org/u/dep/compound.html), [AUX](https://universaldependencies.org/u/pos/AUX.html), [discourse](https://universaldependencies.org/u/dep/discourse.html), [Classical Chinese](https://universaldependencies.org/lzh/).
