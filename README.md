# Annotated-Epigraphic-Corpus-of-Ancient-Italy
## Introduction
The Annotated Epigraphic Corpus of Ancient Italy is a linguistic database focusing on the Italian peninsula in the first millennium BCE. Currently, it covers Messapic, Venetic, the Sabellic languages and epigraphic Latin up to about 100 BCE.

## Purpose of this corpus
Ancient Italy in the first millennium B.C.E. presents a unique trove of linguistic information. Rarely, if anywhere, in the ancient world is such a diversity of languages preserved in so small a region, and their study is of great potential interest to Indo-Europeanists, historical linguists and typologists alike. Unfortunately, however, the accessibility of this data is currently limited: most of the languages of ancient Italy are documented only through printed corpora, and these sometimes lack any kind of linguistic analysis. And where online corpora do exist, they are either incomplete, or lack the level of annotation required for anything more than relatively superficial linguistic research.

This project aims to fill this lacuna by providing *a linguistically oriented and publically available digital research corpus for the languages of Ancient Italy*. As such, it aims to provide the full epigraphic corpus of each of the languages within its purview, along with high-resolution and intercomparable linguistic information for every token. In its present version, the corpus is (almost) complete for the Sabellic, Messapic and Venetic languages, as well as Latin epigraphy before 100 A.D. The current scope of this corpus can therefore informally regarded as the “indigenous” Indo-European languages of Italy.

This corpus was created in the context of a research project on language contact in Ancient Italy and is therefore strongly tailored to the needs of linguistic research (whether synchronic or diachronic in nature), with a particular focus on the intercomparability of these very distinct Indo-European languages. This means that the emphasis lies on linguistic annotation, with less focus on the archaeological and epigraphical context of these texts. However, the Trismegistos link provided for each inscription can be used to track bibliography and metadata, and link the texts in this corpus to other projects, such as EDCS or EDR.

All files are published here as .csv files (utf-16 encoded). The data can be analysed via Python or R, or opened with spreadsheet software such as LibreOffice or Excel. For the benefit of those users who prefer to use spreadsheet software, the final .csv file contains all the corpus data in a single file.

## Contents
The corpus is structured as a relational database, with four primary levels of description, each of which stands in a one-to-many relationship with the immediately subordinate level, as follows:
* [Texts](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/texts.csv) contains information pertaining to individual inscriptions as a whole, such as their dating and provenance.
* [Sentences](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/sentences.csv) contains information on the individual syntactic units of which an inscription is comprised, and provides a relatively basic transcription of the text. Many inscriptions may comprise only a single sentence.
* [Tokens](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/tokens.csv) contains information about the tokens (words and clitics) in a specific sentence, such as its form and (in a future version) its syntactic relations to other tokens.
* [Analysis](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/analysis.csv) provides linguistic analysis of each token. This information is provided on a subordinate level because, particularly in a fragmentary or poorly understood corpus, a token may have more than one possible interpretation. This table offers detailed annotation, ranging from POS-tagging and lemmatisation to semantic categories. It also contains the raw data used for the analysis of the Sabellic TAM system in Pitts (2020).
* [Links](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/links.csv) allows the texts in the database to be linked to extensive metadata and bibliography via their [Trismegistos ID](https://www.trismegistos.org/).

A more detailed contents of all the fields in these tables is provided in the [contents](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/contents.pdf). In addition, the information in the corpus on all levels is also made available as [a single file](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/full_corpus.csv).

## How to cite the corpus
...

## Acknowledgements
This research was carried out with a grant from the [Fonds Wetenschappelijke Onderzoek (FWO) – Vlaanderen](https://www.fwo.be/) (grant no 1150720N).

## Terms of use
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
