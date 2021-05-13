## Introduction
The Annotated Epigraphic Corpus of Ancient Italy is a linguistic database focusing on the Italian peninsula in the first millennium BCE. Currently, it covers Messapic, Venetic, the Sabellic languages and epigraphic Latin up to about 100 BCE.

This database is a work in progress!

## Purpose of this corpus
Ancient Italy in the first millennium BCE presents a unique trove of linguistic information. Rarely, if anywhere, in the ancient world is such a diversity of languages preserved in so small a region, and their study is of great potential interest to Indo-Europeanists, historical linguists and typologists alike. Unfortunately, however, the accessibility of this data is currently limited: most of the languages of ancient Italy are documented only in printed corpora, sometimes without any kind of linguistic analysis. And where digital corpora do exist, they are either incomplete, or lack the level of annotation required for anything more than relatively superficial linguistic research.

This project aims to fill this lacuna by providing *a linguistically oriented and publicly available digital research corpus for the languages of Ancient Italy*. In its present version, the corpus is (almost) complete for the Sabellic, Messapic and Venetic languages, as well as Latin epigraphy before 100 BCE.

This corpus was created in the context of a research project on language contact in Ancient Italy. It is, therefore, strongly tailored to the needs of linguistic research (whether synchronic or diachronic in nature), and focuses on providing high-resolution and intercomparable linguistic information for each attested token in these ancient Indo-European languages. Although there is less emphasis on the archaeological and epigraphical context of these texts, the [Trismegistos link](https://www.trismegistos.org/) provided for each inscription can be used to track bibliography and metadata, and link the texts in this corpus to other projects, such as EDCS or EDR.

All files are published here as .csv files (utf-16 encoded). The data can be analysed via Python or R, or opened with spreadsheet software such as LibreOffice.

## Contents
The corpus is structured as a relational database, with four levels of description, each of which stands in a one-to-many relationship with the immediately subordinate level, as follows:

* [Texts](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/texts.csv) contains information pertaining to individual inscriptions as a whole, such as their dating and provenance.
* [Sentences](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/sentences.csv) contains information on the individual syntactic units of which an inscription is comprised, including a basic transcription of the text. Many inscriptions comprise only a single sentence.
* [Tokens](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/tokens.csv) contains information about the tokens (words and clitics) in a specific sentence, such as their form and (in a future version) their syntactic relations to other tokens.
* [Analysis](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/analysis.csv) provides linguistic analysis of each token. This information is provided on a level subordinate to "Tokens" because, particularly in a fragmentary or poorly understood corpus, a token may have more than one possible interpretation. This table offers detailed annotation, ranging from POS-tagging and lemmatisation to semantic categories. It also contains the raw data used for the analysis of the Sabellic TAM system in Pitts (2020).

In addition, the file [links](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/links.csv) allows the texts in the database to be linked to extensive metadata and bibliography via their [Trismegistos ID](https://www.trismegistos.org/).

A more detailed contents of all the fields in these tables is provided in a [separate pdf file](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/contents.pdf).

## Colophon
General editor: Reuben J. Pitts

For any questions or comments please contact me at reuben.pitts@kuleuven.be.

I would like to thank Toon Van Hal, Freek Van de Velde, Mark Depauw and Tom Gheldof for their help and advice in the making of this corpus.

This research was carried out with a grant from the [Fonds Wetenschappelijke Onderzoek (FWO) – Vlaanderen](https://www.fwo.be/) (grant no 1150720N), in the context of the doctoral project [*The interplay between language contact and language change in a fragmentary linguistic area: the Italic peninsula in the first millennium BCE*](https://www.kuleuven.be/onderzoek/portaal/#/projecten/3H190594?lang=en&hl=en).

## Terms of use
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
