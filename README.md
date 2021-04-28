# Annotated-Epigraphic-Corpus-of-Ancient-Italy
## Introduction
The Annotated Epigraphic Corpus of Ancient Italy is a linguistic database focusing on the Italian peninsula in the first millennium BCE. Currently, it covers Messapic, Venetic, the Sabellic languages and epigraphic Latin up to about 100 BCE.

## Contents
The corpus is structured as a relational database, with four primary levels of description, each of which stands in a one-to-many relationship with the immediately subordinate level, as follows:
* [Texts](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/texts.csv) contains information pertaining to individual inscriptions as a whole, such as their dating and provenance.
* [Sentences](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/sentences.csv) contains information on the individual syntactic units of which an inscription is comprised, and provides a relatively basic transcription of the text. Many inscriptions may comprise only a single sentence.
* [Tokens](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/tokens.csv) contains information about the tokens (words and clitics) in a specific sentence, such as its form and (in a future version) its syntactic relations to other tokens.
* [Analysis](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/analysis.csv) provides linguistic analysis of each token. This information is provided on a subordinate level because, particularly in a fragmentary or poorly understood corpus, a token may have more than one possible interpretation. This table offers detailed annotation, ranging from POS-tagging and lemmatisation to semantic categories. It also contains the raw data used for the analysis of the Sabellic TAM system in Pitts (2020).
* [Links](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/links.csv) allows the texts in the database to be linked to extensive metadata and bibliography via their Trismegistos ID.

A more detailed contents of all the fields in these tables is provided in the [Vademecum](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/Vademecum.pdf). In addition, the information in the corpus on all levels is also made available as [a single file](https://github.com/ReubenJPitts/Annotated-Epigraphic-Corpus-of-Ancient-Italy/blob/main/full_corpus.csv).
