# Unified Annotation Guidelines for Tangut UD v2

## 0. Sentence Boundaries

### 0.1. Core position: a sentence is a grammatical unit, not a translation unit

**A verse unit is not inherently a sentence.** For texts with established stanza divisions, such as Buddhist stanzas consisting of four five-character lines, we nevertheless adopt the established stanza as the sentence unit: one 20-character stanza per sentence. This convention is straightforward and readable, and keeps entity spans and dependency analyses within the stanza.

For example:

> I am mindful that the good spiritual guides are only rarely met even in a koṭī of kalpas. Now, I have succeeded in drawing near to them all and have come here to pay my respects to the Venerable One.
>
> 我念善知識，億劫難值遇；今得咸親近，而來詣尊所。

A stanza may occasionally contain several independent sentences, such as three successive questions. Conversely, a grammatical sentence may extend across two stanzas, with an introductory verb in one stanza and its quotation in the next. Such cases are relatively uncommon, so preserving the established stanza divisions takes priority.

**Translation punctuation does not determine Tangut sentence boundaries.** Full stops and question marks in English or Chinese translations must not be used to establish boundaries in the Tangut text.

For example, the Chinese translation contains the following sequence:

> 彌勒菩薩摩訶薩安處其中，爲欲攝受本所生處父母、眷屬及諸人民，令成熟故；又欲令彼同受生、同修行衆生，於大乘中得堅固故；又欲令彼一切衆生，隨住地、隨善根皆成就故；又欲爲汝顯示菩薩解脫門故，顯示菩薩遍一切處受生自在故，顯示菩薩以種種身普現一切衆生之前常教化故，顯示菩薩以大悲力普攝一切世間資財而不厭故，顯示菩薩具修諸行知一切行離諸相故，顯示菩薩處處受生了一切生皆無相故。

We segment this passage according to the word order and grammatical organization of the Tangut text. Translations may be consulted only when Tangut grammar permits more than one segmentation and grammatical evidence alone cannot resolve the choice. Grammatical criteria retain priority.

### 0.2. Grammatical segmentation criteria

#### 0.2.1. Whole propositions

A sentence is normally an independent unit expressing a complete proposition, with at least one subject–predicate structure. Non-predicative expressions may nevertheless form sentences:

- **Titles**, for example, 𘜶𗣼𗾟𗢳𗤻𗵽𗖰𗚩𘐳𗒹𗰗𗒹𗡪, “大方廣佛華嚴經卷第七十七” (“The Great and Vast Buddha Avataṃsaka Sūtra, Fascicle 77”).
- **Independent interjections or exclamatory expressions**, for example, 𘝶𗦜𘃞。 “何以故？” (“Why is that?”).
- **Fragments**, although this category is not applicable to the Avataṃsaka material.

#### 0.2.2. The tiling principle

Sentence segmentation follows two axioms:

1. Every word in the text must belong to a sentence.
2. Sentences must not overlap.

The resulting segmentation must cover the entire text without gaps or overlaps. If material remains between two complete sentences, that material must constitute at least one additional sentence, even if it is not itself a complete syntactic unit.

#### 0.2.3. Punctuation

If punctuation occurs between A and B, prefer a sentence boundary. If there is no punctuation between them, and the text normally uses punctuation to separate sentences, treat them as parts of a single sentence connected by `parataxis`.

Coordinated structures that share a modifier must remain in the same sentence; otherwise, the shared modifier would lose its attachment site.

#### 0.2.4. The sentence-final particle 𘃞

The suffix 𘃞 occurs at the end of a sentence and generally provides a strong signal that a new sentence begins after it. Some sentences, however, have no overt sentence-final marker.

#### 0.2.5. Exception for very long sentences

- **25 normalized words or fewer:** follow the syntactic criteria strictly; do not split the unit.
- **More than 25 and up to 55 words:** allow editorial discretion over whether to split.
- **More than 55 words:** split the unit, preferably at a predicate-unit boundary. An exception applies where clear markers support retaining the unit; the two examples have clear verbal markers at the end of the sentence.

A typical very long sentence consists of a sequence of subordinate clauses. Although it may grammatically constitute a single sentence, such a unit is difficult to use. Split it at clause boundaries, then return to the regular segmentation criteria as soon as possible.

## 1. Philological Evidence

Preserve the manuscript or base-text spelling in `FORM`. When an erroneous character is confirmed, record the correction using `CorrectForm=…`, `Typo=Yes`, and the corrected `LEMMA`.

## 2. Clause Structure, Arguments, and Modifiers

First identify each clause's predicate, subject, core object, goal, location, instrument, and time expression. Use `nsubj` for the subject, `obj` for a core object, and `iobj` for an additional core argument. Linear proximity alone does not justify an attachment, and a participant's identity does not determine its grammatical role. Use `vocative` only for direct address.

Attach a case marker to the head of the noun phrase it marks using `case`. Use `nmod` for nominal modification of a noun, and `obl` for a nominal non-core modifier of a predicate. Core status must be established for the particular construction. See [UD iobj](https://universaldependencies.org/u/dep/iobj.html) and [UD obl](https://universaldependencies.org/u/dep/obl.html).

## 3. Personal Names and Titles: Core Conventions

| Construction | Internal structure | Receiver of the phrase's external dependency |
|---|---|---|
| A personal name without a title, such as Akṣayamati, Avalokiteśvara, Dharanīṃdhara, Sudhana, or Samantabhadra | The first component is `PROPN`; all remaining `PROPN` components attach directly to it with `flat` | The first name component |
| Personal name + a single nominal title | The first name component attaches to the title with `compound`; the remaining name components still attach to the first with `flat` | The nominal title |
| Personal name + bodhisattva + mahāsattva | Name `compound` → bodhisattva; bodhisattva `compound` → mahāsattva | The final title, mahāsattva |
| Native “being–awakened” expression for bodhisattva | 𘋢 is the `NOUN` head; 𗥤 is `VERB/acl` → 𘋢 | 𘋢; if another title follows, the nominal head attaches onward to that title |
| Maitreya tokenized as a single unit + title | The single `PROPN` attaches to the following title with `compound` | The final nominal title |

For example, 𗉣𗅋𗋃𘋢𗥤 (“intent–without–exhaustion–being–awakened,” Akṣayamati Bodhisattva) has the following structure when numbered 1–5:

- 1 “intent”: `compound` → 4.
- 2 “without” and 3 “exhaustion”: both `flat` → 1.
- 4 “being”: bears the phrase's external relation, such as `nsubj`, `obj`, `iobj`, `obl`, `nmod`, or `root`.
- 5 “awakened”: `VERB/acl` → 4.

When no title is present, component 1 bears the external relation, while components 2 and 3 remain `flat` → 1. Case markers following the name–title phrase, quantifiers applying to the whole phrase, and other modifiers of the whole phrase attach to its actual nominal head.

The same principle applies to other clearly identified names and titles in this corpus, including Śrīsambhava the youth, Śrīmatī the maiden, Śākyamuni Buddha, and Prabhūtaratna Buddha. The internal compounds meaning “youth” and “maiden” are right-headed. “World-Honored One” is a transparent nominal honorific headed by the component meaning “honored one.” Category terms such as Buddha, god, and dragon do not automatically become `PROPN` merely because they occur in a religious context.

## 4. Distinguishing compound, flat, fixed, conj, and appos

All retained `compound` relations in this project point from an earlier component to a later head. `flat`, `fixed`, `conj`, and `appos` are first-headed. Right-headed compounds are a project convention.

Use `compound` only for lexical compounds. Analyze independent conditions, causes, purposes, and coordinated events separately; continuous writing does not justify joining them all with `compound`. Within names, attach every `flat` component directly to the first component rather than forming a chain of `flat` relations. Reserve `fixed` for grammaticalized fixed expressions.

For the totality expression 𗄑𗄑, the first component bears the external relation and the second attaches to it with `fixed`. Classify the expression as `DET/det` when it determines a nominal, as `PRON` when it functions as an independent argument, and as `ADV/advmod` when it functions adverbially. Mark the first component with `ExtPos` to indicate the external part of speech of the whole expression. Do not attach the two adjacent components separately to different nominal heads.

In coordination at the same level, attach each subsequent conjunct directly to the first conjunct. Preserve the hierarchy of nested coordination.

`appos` requires complete nominal expressions standing in an appositional relationship. A comma is not required.

## 5. Part of Speech Depends on the Construction

In nominal compounds containing verbal elements, do not interpret each character's verbal dictionary meaning as a separate event. The same lemma may have different UPOS tags in different constructions.

In this revision layer, `XPOS` mirrors `UPOS`.

## 6. Nominalization, Causation, and Negation Scope

Do not insert a token when no copula is present. Multiple predicates meaning “abode” may form a coordinated structure.

Attach conditional, causal, and purposive clauses to the predicates they actually modify using `advcl`.

Annotate predicate negation consistently as `PART/ADV + advmod + Polarity=Neg`. For negative nominal determination, use `DET/det + PronType=Neg`.

The grammaticalized causative 𗟻 attaches to the lexical predicate with `aux`. A lexical causative with its own arguments and event structure must be analyzed as a lexical construction.

## 7. Auxiliaries and the Segmentation of Traditional Prefixes

An auxiliary attaches to the predicate it actually serves. Register auxiliaries by lemma and by their specific grammatical construction.

Some modal, aspectual, and optative pre-elements, as well as person-agreement elements, are segmented as independent tokens. Directional words retain `ADV/advmod` when they function as independent directional modifiers. Grammaticalized aspectual or modal constructions follow the current `AUX` analysis.

Agreement suffixes may index either the subject or the object. Do not automatically supply a subject merely because a second-person marker is present. See [Kepping 1994](https://doi.org/10.1017/S0041977X00024903). For the directional, perfective, and optative functions of prefixes, see [Arakawa 2021](https://journals.eco-vector.com/1811-8062/article/view/77306). The segmentation and classification adopted in this package remain an explicit analytical convention.
