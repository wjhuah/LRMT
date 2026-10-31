# Summary

The Tangut Universal Dependencies Treebank (MiCA) is a manually annotated treebank of Tangut Buddhist texts, developed by the Mi Corpus Annotation Group.

# Introduction

This treebank is based on the Tangut versions of the *Lotus Sutra* (法華經) and the *Avataṃsaka Sūtra* (華嚴經). The texts are transcribed from published images of Tangut manuscripts and annotated according to Universal Dependencies v2.

Original Tangut manuscripts generally contain no punctuation between words or sentences. For UD annotation, punctuation is added editorially according to grammatical structure. Word segmentation follows lexical and syntactic criteria. The treebank provides lemmas, universal part-of-speech tags, morphological features, dependency relations, and lexical glosses and transliterations in `MISC`.

The current release contains one file:

* `txg_mica-ud-test.conllu`
    - Chapter 25 of the *Lotus Sutra* (法華經・觀世音菩薩普門品), based on the manuscript transcription published by Chen Bingying (1985).
    - Volume 77 of the *Avataṃsaka Sūtra* (華嚴經), based on the manuscript transcription published by Arakawa Shintarō (2011).

The initial release contains approximately 14,000 tokens in 503 sentences. All annotated data are currently included in the test set. No separate training or development sets are provided. The two source texts can be distinguished by the prefixes `lotus_sutra_` and `avatamsaka_sutra_` in the sentence identifiers.

The texts include both prose and verse. The annotation follows the UD v2 guidelines, with language-specific conventions documented in the [Tangut UD guidelines](https://universaldependencies.org/txg/).

# Acknowledgments

We thank Tak Wai Wong for permission to use his earlier [Universal Dependencies annotations of the Tangut Lotus Sutra](https://twwspes.github.io/annodoc/saddharmapundarika_sutra/24_tangut).

We thank Xun Gong for permission to consult his work on Tangut pronunciation and lexical interpretation. Romanizations are based on the [Tangut Pronunciation Database](https://github.com/semakosa/tangut-pronunciation-db), which is subject to its own Limited Public Use License. The pronunciation database itself is not redistributed.

The English translation of the *Lotus Sutra* is taken from [500 Yojanas, Chapter 25](https://www.500yojanas.org/lotus-sutra/chapter25/), identified by the project as licensed under CC BY. The English translation of the *Avataṃsaka Sūtra* is based on Bhikshu Dharmamitra, *The Flower Adornment Sutra* (Kalavinka Press, 2022), with permission for partial use.

Lexical glosses refer in part to [TangutTranslator](https://github.com/C27Ezx/TangutTranslator/blob/main/tangut_learning_data.json), originally based on Alan Downes and [Tangut.info](https://tangut.info/), with additional corrections informed by Xun Gong's *Tangut: An Introductory Reader*. Dictionary files are not redistributed.

# References

* Chen Bingying (陈炳应). 1985. 图解本西夏文《观音经》译释. 敦煌研究.
* Arakawa, Shintarō. 2011. [An Annotated Japanese Translation of the Tangut Version of Avataṃsaka Sūtra, Vol. 77 in the Princeton University Collection](https://tufs.repo.nii.ac.jp/record/2077/files/jaas081006_ful.pdf). Journal of Asian and African Studies 81:147–305.
* Kepping, Ksenia B. 1994. [The Conjugation of the Tangut Verb](https://doi.org/10.1017/S0041977X00024903). Bulletin of the School of Oriental and African Studies 57(2):339–346.
* Beaudouin, Mathieu. 2023. [Tangut and Horpa Languages: Some Shared Morphosyntactic Features](https://doi.org/10.1075/lali.00142.bea). Language and Linguistics 24(4):611–673.
* Ji, Yue. 2026. [The Sigmatic Perfect 𗭪 sji² in Tangut and Its Grammaticalization](https://doi.org/10.1075/lali.00266.ji). Language and Linguistics 27(4):710–734.

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
