# MiCA: Mi (𗼇) Corpus Annotation Group

MiCA develops multilayer corpora and other NLP resources for Tangut texts (𗼇𘝞).

<p align="center">
  <img src="assets/tangut-logo.png"
       alt="Tangut logo"
       height="180"
       style="vertical-align: middle;">
  &nbsp;&nbsp;&nbsp;
  <img src="assets/mica-logo.png"
       alt="MiCA logo"
       height="180"
       style="vertical-align: middle;">
</p>

## Contents

MiCA provides the following resources:

| Resource | Description |
|---|---|
| `corpus/` | 12 Open-source Tangut texts. |
| `treebank/` | Universal Dependencies (UD) treebank for Tangut (𗼇𘝞𘕰𗾊). |
| `dictionary/` | Dictionary used in UD_Tangut-MiCA. |
| `MiCA-guideline.md` | Tangut UD annotation guidelines. |
| `copyright.md` | Source attribution, permissions, and copyright information. |

## Universal Dependencies

Our central component is the development of a UD treebank for Tangut (𗼇𘝞𘕰𗾊), **[UD_Tangut-MiCA](/treebank/txg_mica-ud-test.conllu)**, which is for inclusion in the next UD release.

Note: The **[official UD treebank repository](https://github.com/UniversalDependencies/UD_Tangut-MiCA)** is the authoritative source for released treebank data.

## Corpus

The [`corpus/`](corpus/) directory contains 12 open-source digitized Tangut texts.

- [`華嚴經.txt`](corpus/華嚴經.txt): Tangut text transcribed from 荒川慎太郎 (2011), [プリンストン大学所蔵西夏文華厳経巻七十七訳注](https://tufs.repo.nii.ac.jp/records/2077).
- [`妙法蓮華經普門品.txt`](corpus/妙法蓮華經普門品.txt): Tangut text transcribed from 陈炳应 (1985), 图解本西夏文《观音经》译释, *敦煌研究*.
- [`聖起源之歌.txt`](corpus/聖起源之歌.txt): Tangut text retrieved from [Wikisource](https://wikisource.org/w/index.php?oldid=1032800).
- [`新集碎金置掌文.txt`](corpus/新集碎金置掌文.txt): Tangut text retrieved from [Wikisource](https://wikisource.org/w/index.php?oldid=1112616), based on IOM Inv. 741, with corrections from Inv. 742V.
- [`高王觀世音經.txt`](corpus/高王觀世音經.txt): Tangut text retrieved from [Wikisource](https://wikisource.org/w/index.php?oldid=987774), based on *中國藏西夏文獻* (2005), vol. 12, pp. 402–408.
- [`月月樂詩.txt`](corpus/月月樂詩.txt): Tangut text retrieved from [Wikisource](https://wikisource.org/w/index.php?oldid=1186555), based on 西田龍雄 (1986), [西夏語『月々楽詩』の研究](https://repository.kulib.kyoto-u.ac.jp/dspace/bitstream/2433/73030/1/KJ00000077757.pdf).
- [`金剛般若波羅蜜經.txt`](corpus/金剛般若波羅蜜經.txt): Tangut text retrieved from [Wikisource](https://wikisource.org/w/index.php?oldid=1030376), based on Dunhuang Research Academy G11·035 and Wuwei Municipal Museum G31·015.
- [`新刻二十五問答.txt`](corpus/新刻二十五問答.txt): Tangut text retrieved from [Wikisource](https://wikisource.org/w/index.php?oldid=909636), based on Kirill Solonin (2012), [The Chán Teaching of Nányáng Huìzhōng (-775) in Tangut Translation](https://doi.org/10.1163/9789004233454_012).
- [`大悲觀音陀羅尼.txt`](corpus/大悲觀音陀羅尼.txt): Tangut text retrieved from [Wikisource](https://wikisource.org/w/index.php?oldid=909689), based on 段玉泉 (2014), "A Textual Research on the Tangut Version of Mahākāruṇika-nāma-ārya-avalokiteśvara dhāraṇī," *Central Asiatic Journal* 57, pp. 99–109.
- [`涼州感應塔碑.txt`](corpus/涼州感應塔碑.txt): Tangut text retrieved from [Wikisource](https://wikisource.org/w/index.php?oldid=909760), based on 西田龍雄 (1964), 西夏文 涼州感應塔碑文 解讀, *西夏語の研究*, vol. 1, pp. 156–176.
- [`新集錦合辭.txt`](corpus/新集錦合辭.txt): Tangut text retrieved from [Wikisource](https://wikisource.org/w/index.php?oldid=1021341), based on E. I. Kychanov (1974), *Вновь собранные драгоценные парные изречения*, and 聶鴻音 (2007), *西夏遺文錄*.
- [`音同重校序.txt`](corpus/音同重校序.txt): Tangut text retrieved from [Wikisource](https://wikisource.org/w/index.php?oldid=1186812), based on 聶鴻音 (2007), 西夏遺文錄, *西夏學* 2, p. 160.

## Related Resources

The following projects provide additional resources for Tangut research.

- **[Open Tangut](https://github.com/imlooh/open-tangut)** — Tangut character and multilingual lexical resources.
- **[Tangut Pronunciation Database](https://github.com/semakosa/tangut-pronunciation-db)** — Historical pronunciation and reconstruction data maintained by Xun Gong.
- **[Tangut Text](https://github.com/tinbreaker/tangut-text)** — Digitized Tangut textual resources.
- **[Tangut Rhyme Dictionaries Data](https://github.com/nkay0/Tangut-rhyme-dictionaries-data)** — Digital resources for Tangut rhyme dictionaries.
- **[TangutIDS](https://github.com/JLHwung/TangutIDS)** — Ideographic description sequences for Tangut characters.

Please consult each project's documentation and licensing terms before reusing its data.

## Current Members

- Hua, Wenjie (Georgetown University)
- Ji, Yue (University of Vienna)
- Jiang, Zhengshi (University of Washington)
- Lin, Chia-Wei (University of Lausanne)
- Zeldes, Amir (Georgetown University)
- Zhang, Longyu (Ghent University)
- Zheng, Yuxi (Peking University)

We welcome collaborations! For inquiries or contributions, please contact:

wh583 AT georgetown DOT edu

## License

- **Any materials by MiCA:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/), where the contributors hold the necessary rights.
- **UD treebank:** [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/), consistent with the official [UD_Tangut-MiCA](https://github.com/UniversalDependencies/UD_Tangut-MiCA).
- **Corpus:** Public-domain texts remain in the public domain. Transcription work is not copyrightable.
- **Third-party resources:** Retain their respective licensing conditions.

See [copyright.md](copyright.md) for detailed source attribution.
