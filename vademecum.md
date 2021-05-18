*Annotated Epigraphic Corpus of Ancient Italy, version 1.0*

*The following document provides a detailed field-by-field usage guide, description of contents, and methodological information for the database.*

# 1. Texts
This table contains information pertaining to individual inscriptions as a whole. All information in this table was either entered manually, or entered through collaboration with Trismegistos and then manually completed.

## 1.1. Links
**Text_ID**: The ID of the inscription within this corpus. This number can be used to link this table to other tables (sentences.csv and links.csv).

**Reference**: A single bibliographical reference for this inscription, typically its reference in the principal printed corpus in general use. For instance, the corpus aims to provide the CIL reference for Latin inscriptions and Crawford for Sabellic. As of version 1.0 this field is still under construction.

**Name**: The informal name of the inscription. For instance, values of this field include Fibula Praenestina and Iguvine Tables. This field currently contains values for only a select few texts.

## 1.2. Language information
**Language**: The main language in which the inscription is written. Values in the corpus are Latin, Oscan, Umbrian, Old Sabellic, Messapic and Venetic.

**Language_Family**: The higher-level classification of the main language of the inscription. For instance, Latin is classified as Indo-European::Italic::Latino-Sabellic. This classification is maximalist and includes speculative levels (such as placing Messapic under “Balkan”), to allow for maximal search possibilities.

**Language_Variety**: This is generally equivalent to “Language”, but may specify a variety on a lower taxonomic level. For instance, in line with recent research (Bakkum 2009), this corpus classes Faliscan as a variety of Latin.

**Script**: The alphabet or script in which the inscription is written. This is relevant mostly for Sabellic, which was written in various scripts.

## 1.3. Chronological information
**Date_after**: The earliest possible date of this inscription.

**Date_before**: The latest possible date of this inscription.

## 1.4. Provenance
**Provenance**: The location (town or city) in which this inscription was found. In some cases inscriptions are known to have been written in a different location to where they were found. In those cases, provenance provides the location where the text was written.

**GeoID**: The ID allocated to this location by Trismegistos.

**Latitude**: The latitude of this location.

**Longitude**: The longitude of this location.

## 1.5. Additional information
**Finite_verb**: This field returns the value TRUE if the inscription in question contains at least one finite verb form, FALSE otherwise. The purpose of this field is to search specifically for inscriptions that constitute full sentences (as opposed to inscriptions containing only names, for instance).

This field was automatically generated by searching through the “POS_code” field of all analyses associated with a specific inscription.

**Analysable_token**: Similar to the above, but broader, this field returns TRUE if the inscription contains at least one token with a linguistic analysis. This allows the user to sift out inscriptions which are wholly unintelligible or, for instance, contain only single letters.

This field was automatically generated by searching through the “POS_code” field of all analyses associated with a specific inscription.

**Text_length**: The number of individual tokens this text links to. This is essentially a count of the number of words (and clitics) that the inscription contains.

This field was automatically generated by counting the number of non-blank tokens associated with a specific inscription.

# 2. Sentences
This table contains information pertaining to individual syntactic units (sentences) within a given inscription. Frequently, an inscription contains only a single syntactic unit.

## 2.1. Links
**Text_ID**: The ID of the inscription to which this sentence pertains (allowing this table to be linked to texts.csv).

**Sentence_ID**: A fixed and unique number referring to this specific sentence (allowing this table to be linked to tokens.csv).

**Sentence_position**: A number which keeps track of the order of sentences within an inscription. This counter starts from 1 in every new inscription and is therefore not a unique ID.

## 2.2. Sentence
**Sentence**: This field contains the full text of the sentence in question.

Since the focus of this corpus is linguistic, not epigraphic, the resolution here is low. The text provided is a trimmed-down version of the text provided by published corpora, either printed or online (or papers in which more recent inscriptions appear).

This field is meant only for convenient reference and should on absolutely no level be considered as an alternative to consulting an epigraphic apparatus.

**Section**: In the rare cases where a text is long enough that a subdivision into larger units than sentences, this field keeps track of them. Currently this applies only to the Iguvine Tables (where this field keeps track of tables running from I to VIIb).

This information was added manually.


 # 3. Tokens

This table contains information on individual tokens within a syntactic unit, usually words or enclitics.

## 3.1. Links

**Text_ID**: The ID of the inscription to which this token pertains (allowing this table to be linked to texts.csv).

**Sentence_ID**: The ID of the sentence to which this token pertains (allowing this table to be linked to sentences.csv).

**Sentence_position**: A number which keeps track of the order of sentences within an inscription. This counter starts from 1 in every new inscription and is therefore not a unique ID.

**Token_ID**: A fixed and unique number referring to this specific token (allowing this table to be linked to analysis.csv).

**Token_position**: A number which keeps track of the order of tokens within a sentence. This counter starts from 1 in every new sentence and is therefore not a unique ID.

## 3.2. Token

**Token**: The token itself.

**Token_clean**: This field is intended for ease of searching. It reproduces the token stripped of all special or non-alphabetic characters, and in transliteration where a non-Latin symbol is used.

The field was automatically generated using the unidecode module in Python, with a small number of modifications (to remove non-alphabetic characters, and to ensure that, for instance, Greek lunate sigma manifests as “s” rather than “c”).

## 4.5 Syntax

Syntactic information is provided on the level of Token, not Analysis, because it concerns the way in which tokens relate to each other. It is therefore tricky to incorporate multiple possible syntactic analyses into the design of a corpus, and this has been avoided.

A dependency grammar model is adhered to for syntactic annotation, in line with much recent work on computational approaches to ancient Greek and Latin syntax.

The corpus largely follows v. 1.3. of the [Perseus guidelines](http://static.perseus.tufts.edu/docs/guidelines.pdf) for the syntactic annotation of Latin. A few modifications have been implemented for features that are unsuited for the annotation of an epigraphic corpus. For instance, the corpus does not assign syntactic roles to sentence punctuation, which is typically absent from epigraphic inscriptions and is therefore primarily an editorial choice. Instead, blank tokens (with “-” in the Token field) are used to fill syntactic roles that are not represented by actual tokens in the text.

These fields are a work in progress: currently, data is included for most Sabellic, Venetic and Messapic inscriptions containing at least one verb.

All information was added manually.

**Relation**: This field describes the syntactic relationship in which this token stands to its head. A full list of tags can be found in the link above.

**Head**: The Token_ID of the syntactic head of the current token. The value of this field is 0 (zero) if there is no head.

 
# 4. Analysis
This table provides morphological information. This information is provided on a level subordinate to tokens, because in an obscure or fragmentary text it is possible for a given token to have multiple plausible analyses.

Currently, the focus lies on providing a single plausible analysis for every token. Most tokens therefore correspond to only one analysis. In future, this data will be expanded to reflect differences of opinion in the academic literature.

Except where indicated otherwise, the data in this table was annotated manually. Often, however, an initial analysis was first created automatically and then corrected. Specifically:

* For Latin an initial morphological analysis was attempted using [Morpheus](http://www.perseus.tufts.edu/hopper/xmlmorph?lang=lat&lookup=fibula).

* For Sabellic, Venetic and Messapic, dictionaries of all attested forms were first prepared, which were then linked to the tokens by string searches or fuzzy-searches (with the *fuzzywuzzy* module in Python).

Unsurprisingly, however, an epigraphic corpus is “messy” and does not lend itself well to this kind of shortcut, so all of the data underwent extensive manual correction.

## 4.1. Links
**Text_ID**: The ID of the inscription to which this analysis pertains (allowing this table to be linked to texts.csv).

**Sentence_ID**: The ID of the sentence to which this analysis pertains (allowing this table to be linked to sentences.csv).

**Sentence_position**: A number which keeps track of the order of sentences within an inscription. This counter starts from 1 in every new inscription and is therefore not a unique ID.

**Token_ID**: The ID of the token to which this analysis pertains (allowing this table to be linked to tokens.csv).

**Token_position**: A number which keeps track of the order of tokens within a sentence. This counter starts from 1 in every new sentence and is therefore not a unique ID.

**Analysis_ID**: A fixed and unique number referring to this analysis.


## 4.2. Lemmatisation

**Lemma**: The lemma to which the current token belongs.

Note that the lemma field does not disambiguate homonyms. Thus, searching dico will return forms of dicare and dicere without fear or favour. This avoids the need to resort to arbitrary and confusing disambiguations such as *dico_2*. If one wishes to find only forms of dicere, use this field in combination with “morphological type” to specify the conjugation.

The lemma is the dictionary form in Latin (masculine nominative singular for nominal forms, active present indicative first person singular for verbs). For other Italic languages, where such a dictionary form is usually not attested, it is a regularised form of the root (e.g. *deyk* in Sabellic). The conventions used for regularising the lemma are not exactly equivalent for all languages in the corpus (although they are, of course, internally consistent): cross-linguistic lemma searches should use the field “Classical_Latin_equivalent”, as described below.

**Lemma_simplex**: Usually equivalent to “Lemma”, except that this field gives the simplex form of a compound lemma. For instance, the “Lemma” entry for the token *perfecerit* is *perficio*, while the “Lemma_simplex” is simply *facio*.

**Lemma_frequency**: The number of times this particular value occurs in the “Lemma” field in this language. As noted above, be aware that “Lemma” does not discriminate between homonyms.

**Language**: The language this token is analysed as belonging to. This field may differ from the “main language” of the inscription as a whole (provided in texts.csv), as inscriptions often contain tokens in multiple languages. In addition, the same token may have different possible analyses in different languages.

## 4.3. Morphology

Since the aim of this corpus is to facilitate comparison between different ancient languages, it strives for a maximally descriptive (and therefore linguistically accurate) terminology in its morphological analyses. For ease of reference, the field POS_code converts the conventions employed here into standard POS tags.

**Morphological_type**: This field keeps track of inflectional declensions and conjugations, usually based on the final or characteristic sound of the stem.

The terms used are descriptive, and based on the final or characteristic sound of the stem. The Latin “first declension” thus appears as “A-stem”. This terminology is less arbitrary than the traditional terms and facilitates intercomparison between the languages involved.

For nouns:

Annotated as|description
---|---
A-stem|first declension (type *mensa*)
O-stem|second declension (type *mensa*)
YO-stem|second declension (type *Lucius*) (relevant only in some languages)
C-stem|third declension (type *rex*)
I-stem|third declension (type *turris*) (not distinguished from C-stem in Latin)
U-stem|fourth declension (type *fructus*)
E-stem|fifth declension (type *dies*)

For verbs:

Annotated as|description
---|---
A-stem|first conjugation (type *amo*)
E-stem|second conjugation (type *moneo*)
thematic|third conjugation (type *rego*)
Ī-stem|fourth conjugation (type *audio*)
I-stem|fifth conjugation (type *facio*)

General:

Annotated as|description
---|---
INDECL|indeclinable, e.g. *ita, de, frugi*
IRR|wide variety of stems, e.g. *sum, eo, qui…*

**Part_of_speech**: The part of speech of the token analysed (noun, verb, etc.).

Current values include: noun, verb, adjective, pronoun, adverb, adposition, conjunction, negation and particle.

Although part of speech is usually a lexical property of words, it is occasionally treated as an inflectional category. For instance, *bene* is annotated as a form of the lemma *bonus*, with “adverb” instead of “adjective” as its part of speech.

**Stem**: This field keeps track of basic stem categories which host morphological inflection. These include the present and perfect stems of Latin verbs, but also, for instance, the degrees of comparison of adjectives.

Current values include:

Annotated as|description
---|---
present|any form based on the present stem of verbs, e.g. *reg*- for *rego*
perfect|any form based on the perfect stem of verbs, e.g. *rex*- for *rego*
preterite|a stem which hosts past tense morphology (used as generic term for a past tense stem in non-Latino-Faliscan languages, where the term “perfect” may be inappropriate)
aorist|the aorist stem (only in Greek)
sigmatic|an extraparadigmatic sigmatic stem (e.g. *faxis* or *amassis* in Latin)
PPP|A form based on the Italic perfect passive participle or supine stem (fourth principal part), so *rect*- for *rego*.
other|Any (often extraparadigmatic) verb stem which does not fit into the above categories, such as Sabellic *fust* or Latin *duim*
comparative|The comparative degree of adjectives or adverbs. Note that the positive degree is assumed by default and is not annotated.
superlative|The superlative degree of adjectives or adverbs.
diminutive|A diminutive form of a noun or (less typically) adjective.

**Tense**: Tense includes any category denoting temporal distinctions. For the Latin present stem this would include simple (e.g. *amo*), future (*amabo*) and past (*amabam*). Note that the perfect indicative is also analysed as the “simple” (unmarked) tense form, whereas “past” is reserved for the pluperfect.

Current values are:

Annotated as|description
---|---
simple|a verb stem without additional marking for tense (e.g. present *rego* or perfect *rexi*)
future|a verb stem marked for futurity (e.g. future *regam* or future perfect *rexero*)
past|a verb stem marked for anteriority (e.g. imperfect *regebam*, imperfect subjunctive *rexerem*, pluperfect *rexeram*, pluperfect subjunctive *rexissem*.

**Mood**: The mood of the token analysed.

In line with some traditional grammatical analysis, it has been found convenient to group nominal forms of verbs (participle, gerundive, infinitive, supine) in this category as well: although these are not modal categories, they are in complementary distribution with modal exponents.

Current values are indicative, subjunctive, optative, imperative, infinitive, gerundive, participle and supine.

**Diathesis**: The grammatical voice or diathesis of the token analysed. Current values are active and passive.

**Person**: The grammatical person of the token analysed. Alphabetic indices are used rather than numeric indices to ensure that spreadsheet software (such as Excel) treats the values as strings (so A, B and C for first, second and third person, respectively).

**Number**: The grammatical number of the token analysed. Current values are singular, plural and (occasionally) dual.

**Gender**: The gender of the token analysed. Current values are M, F and N (for masculine, feminine and neuter, respectively).

**Case**: The grammatical case of the token analysed. Current values are:

Annotated as|description
---|---
NOM|nominative
VOC|vocative
ACC|accusative
GEN|genitive
DAT|dative
ABL|ablative
LOC|locative
INS|instrumental

**Category**: This is a catch-all field for any categorial distinction not captured by the above. It assigns alphabetic indices (A, B, C...). Currently this is applicable only to the Latin imperatives *ama* and *amato*, which are labelled imperative A and imperative B in the corpus.

**POS_code**: To facilitate intercomparability with other projects, this field translates the morphological analysis provided above into conventional 9-slot POS tags. These tags are generated automatically based on string searches in the preceding fields.

**Tags**: This field is similar to the above, in that it provides a succinct summary tag with morphological information, but it does so in human-readable form. For instance, “perf-3-sg” or “M-nom-pl.”

As is apparent from the first example, for the sake of brevity and convenience some categories have default values (thus “indicative”, “active” and “present” are not explicitly signalled).

These tags are generated automatically based on string searches in the preceding fields.

## 4.4. Semantic information

**Meaning**: A short English translation of the token in question. This was added manually in all cases except for Latin, where an initial translation was added based on [Whitaker’s Words](https://archives.nd.edu/words.html) and then manually corrected.

**Meaning_category**: This organises a number of lemmata into very broad semantic categories. The corpus currently contains:

* PROPER (for proper names e.g. Manius, Zeus, Roman)

* RELATION (e.g. daughter, son-in-law, mother)

* HUMAN (e.g. slave, praetor, flute-player)

* BODY (e.g. head, hand, liver)

* ANIMAL (e.g. horse, sheep, lion)

* VICTUALS (e.g. water, wine, meal)

* NUMBER (e.g. three, twice, fourth)

* POSSESSIVE (e.g. your, his, my)

* BUILDING (e.g. house, statue, bridge)

* MATERIAL (e.g. gold, silver, wood)

* COLOUR (e.g. white, black, red)

* TIME (e.g. day, year, hour)

* GEOGRAPHY (e.g. sea, river, field)

* POLITICS (e.g. vote, assembly, plebs)

* LAW (e.g. fine, judge, punishment)

* ECONOMY (e.g. money, debt, sell)

* RELIGION (e.g. goddess, sacrifice, pray)

**Meaning_subcategory**: This is currently used only to distinguish different categories of proper name, and contains the values PERSONAL, TOPONYM and THEONYM.

**Classical_Latin_equivalent**: This field contains a close cognate or semantic equivalent of the current lemma in orthographically standardised classical Latin. This field is more consistent and regularised than the “Translation” field above, and therefore facilitates intercomparison between different languages.

For instance, one may wish to find all occurrences of a first person pronoun in Italic languages. One can do so simply by searching *ego* in this field.

This field also standardises Old Latin forms to classical Latin. Thus the Old Latin verb *to, tare* “to steal”, for instance, becomes furor in this field.

**Classical_Latin_form**: Equivalent to the above, but the classical Latin equivalent is here appropriately inflected, rather than simply giving a dictionary form.

This field was initially generated automatically, using a modified version of the software underlying [Whitaker’s Words](https://archives.nd.edu/words.html). Its output was then corrected manually (not yet complete for version 1.0).

**TAM_analysis**: Information on the tense, aspect and modality of verb forms. This column contains the data used for Pitts (2020) and is limited to finite verb forms in Sabellic. All data was entered manually.

## 4.5. Phonology and orthography

**Standard_aligned**: This field contains a standardised form of the current token which has been aligned (using hyphens) with the attested form of said token in the following field. For instance, for analysis ID #1469381, these fields read:

* Standard_aligned: cu-raverunt

* Form_aligned: coeraveront

Since the alignment guarantees that both strings are the same length, they can be searched with regular expressions to gather data on sound changes (e.g. monophthongisation) or orthographic variants (e.g. the use of gemination, or the use of k, q and c).

Currently these fields contain data for Latin and Sabellic. However, the field Standard_aligned contains somewhat different data for these languages. In the case of Latin, the “standard” form is simply the classical Latin form, equivalent to the field Classical_Latin_form (except aligned). For Sabellic, however, the field contains one of the older etymological forms suggested in Unterman (2000).

Currently the Latin alignment is automatic (using the alignment functions in the historical linguistics module LingPy). The Sabellic data were aligned manually.

**Form_aligned**: See above.
	
# Links

This table links to texts.csv and serves to link the corpus to extensive metadata and bibliographical information hosted by Trismegistos.

**Text_ID**: The ID of the text in this corpus (links to texts.csv)

**Trismegistos_ID**: The ID of this text in the Trismegistos project.