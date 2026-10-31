# Summary

The Tangut Treebank (MiCA) is an annotated treebank of Tangut texts, developed by the Mi Corpus Annotation Group.

# Introduction

This treebank is based on the Tangut versions of the *Lotus Sutra* (法華經) and the *Avataṃsaka Sūtra* (華嚴經), include both prose and verse. Texts are transcribed from published images of manuscripts and annotated according to Universal Dependencies v2.

Original Tangut manuscripts generally contain no punctuation between words or sentences. For UD annotation, punctuation is added. Word segmentation follows lexical and syntactic criteria. The treebank provides lemmas, universal part-of-speech tags, morphological features, dependency relations, and lexical glosses and transliterations in `MISC`.

The current release contains one file:

* `txg_mica-ud-test.conllu`
    - Chapter 25 of the *Lotus Sutra* (法華經・觀世音菩薩普門品), based on the manuscript transcription published by Chen Bingying (1985).
    - Volume 77 of the *Avataṃsaka Sūtra* (華嚴經), based on the manuscript transcription published by Arakawa Shintarō (2011).

The release contains approximately 14,000 tokens in 503 sentences. All annotated data are currently included in the test set. The two source texts can be distinguished by the prefixes `lotus_sutra_` and `avatamsaka_sutra_` in the sentence identifiers. 

# Acknowledgments

We thank Tak Wai Wong for permission to use his earlier [Universal Dependencies annotations of the Tangut Lotus Sutra](https://twwspes.github.io/annodoc/saddharmapundarika_sutra/24_tangut).

We thank Xun Gong for permission to use his work on Tangut [pronunciation](https://github.com/semakosa/tangut-pronunciation-db) and glossary (Reichert Verlag, forthcoming), subject to its own Limited Public Use License.

The English translation of the *Lotus Sutra* is taken from [500 Yojanas](https://www.500yojanas.org/lotus-sutra/), under CC BY. The English translation of the *Avataṃsaka Sūtra* is based on Bhikshu Dharmamitra, [*The Flower Adornment Sutra*](https://kalavinka.org/#A_Complete_Translation_of_the_Avatam%CC%A3saka_Sutra) (Kalavinka Press, 2022), with kind permission for partial use. We thank them.

Lexical glosses refer in part to [TangutTranslator](https://github.com/C27Ezx/TangutTranslator/blob/main/tangut_learning_data.json), based on Alan Downes's [Tangut.info](https://tangut.info/). We thank them.

# Changelog

* 2026-11-15 v2.19
  * Initial release in Universal Dependencies.
  * Tangut annotations of the *Lotus Sutra* and the *Avataṃsaka Sūtra*.

<pre>
=== Machine-readable metadata (DO NOT REMOVE!) ================================
Data available since: UD v2.19
License: CC BY-SA 4.0
Includes text: yes
Parallel: no
Genre: narration poetry
Lemmas: manual native
UPOS: manual native
XPOS: not available
Features: manual native
Relations: manual native
Contributors: Hua, Wenjie; Lin, Chia-Wei; Zheng, Yuxi; Ji, Yue; Zhang, Longyu; Zeldes, Zhengshi Jiang, Amir
Contributing: here
Contact: wh583@georgetown.edu
===============================================================================
</pre>
