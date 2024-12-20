# Corpus Coranicum - TEI DATA

TEI Data for the Digital Project "Corpus Coranicum" (https://corpuscoranicum.de)

This is a TEI ([Text Encoding Initiative](https://tei-c.org/)) Export of the Corpus Coranicum project, which ran from 2007 to 2024 at the [Berlin Brandenburg Academy of Sciences and Humanities (BBAW)](https://www.bbaw.de/forschung/corpus-coranicum).
* The dataset that forms the basis of this export comes from other XML project files and from the project's MySQL database.
* A full list of contributors to the Corpus Coranicum Project can be seen here:  https://corpuscoranicum.de/en/about/team.
* The TEI schema for this TEI dataset was developed by Yasmin Faghihi (Cambridge) and Huw Jones (Cambridge).
* Claus Franke (BBAW - TELOTA) and Marcus Lampert (BBAW - TELOTA) did the technical implementation of feeding the project data into the TEI schema.

## Technical Information

* As indicated in beginning of each XML document, the TEI validates against a unified `corpus_coranicum.rng` schema. One can validate the TEI export with something like this: `find . -name '*.xml' -print | parallel --tag jing ./schema/corpus_coranicum.rng > validation.txt`

## Summary of TEI Dataset

* `cairo_quran`: The 1924 Cairo edition of the Quran, including English, German, and French translations.
* `quran_commentary`: Chronological, literary-critical commentary on the Quran, organized by Sura and time period in which the Suras where likely written.
* `quran_concordance`: A full grammatical parse of every word in the Quran, based on the concordance of Rafael Talmon (1948-2004).
* `quran_intertexts`: A database of intertextual connections between the Quran and various texts from late antiquity and earlier.
* `quran_manuscripts`: Information on over Quran 2500 manuscripts dating from around 650 to the present.
* `quran_variants`: Variant readings of the Quran included in early sources of Muslim scholarly tradition.

## Detailed Overview of the TEI Dataset

### General considerations

This is to document the TEI dataset, which was produced as the result of
a transform from the Corpus Coranicum dataset originally created in a
SQL database. General principles across all file types included:

-   Use of xml:id attributes to uniquely identify core elements in the
    dataset

-   Use of key attributes to create mappings both between and across
    files

While in general we followed standard TEI practice for data
compatibility, we did make certain adjustments to the schema to reflect
project specific practice.

Creators of the file were recorded using respStmt elements and
taxonomies were recorded in the classDecl element.

### File Types

**cairo_quran**: This file contains the transcription of the 1924 Bulaq edition of the
Qur'an. It was modelled using the standard TEI elements for
transcription with each Surah, verse and word given a unique id. Linke
to images were also encoded in the standard way, using facsimile,
surface and graphic elements.

**quran_commentary**: This was modelled with one file for each commentary and filenamed
according to each Surah by number. Each file contains the text of the
surah, the translation and the commentary, encoded using standard TEI
transcription elements. In the commentary text, references to surahs
were linked using xml:id and target attributes. Bibliographic references
were encoded with bibl elements and linked with ids. The different
sections in the commentary were separated using div elements with type
attributes.

**quran_concordance**:  This was modelled with one file for each surah and filenamed according
to the surah number. Each word was divide up into typed segments, using
a standard vocabulary developed by the project.

**quran_intertexts**: This directory contains one file on texts predating the Qur\'an, named
categories.xml. All other files are named according to the intertext id.
Information on each intertext is recorded using the msDesc module for
manuscript description and is transcribed and translated in the text
section.

**quran_manuscripts**: This was modelled with one file for each manuscript, filenamed according
to the manuscript id. The msDesc module was used for manuscript
description with ids used to reference the sections of the Qur'an.
References to images were encoded in the standard way using the
facsimile, surface and graphic elements.

**quran_variants**: This directory consists of three files:
- allvariants: contains a list of variant readings including the reader,
the source of the variant and the variant itself. All elements are keyed
to the relevant authority files.
- reader: an authority file of the readers referred to in the allvariants
file.
- sources: an authority file of the sources referred to in the allvariants
file.

### Schema
This directory contains the ODD and rng files for the customisations
necessary for the project. These were:

-   added controlled values for the form attribute on objectDesc element

-   added type attribute to the bibl element

-   added controlled values for the type attribute on decoNote element

-   added extra value to list for type attribute on dimensions element

-   added documentation to the extent element

-   added controlled values and documentation for script attribute on
    handNote element

-   added controlled values and documentation for calendar attribute on
    origDate element

-   added controlled values and documentation for datingMethod attribute
    on origDate element

-   added documentation to n attribute on origPlace element

-   added controlled values and documentation for type attribute on
    provenance element

-   added documentation to repository element

-   added controlled values and documentation for material attribute on
    supportDesc element

-   added documentation to avaalbility element

-   added controlled values and documentation for type attribute on
    change element

-   added controlled values and documentation for type attribute on
    colophon element

-   added controlled values and documentation for type attribute on
    listBibl element

-   added controlled values and documentation for type attribute on
    msDesc element

-   added controlled values and documentation for type attribute on note
    element

-   added documentation for projectDesc element

-   added controlled values and documentation for type attribute on
    title element

-   added controlled values and documentation for script and style
    attributes on scriptNote element

-   changed the key attribute on the person element to accept a wider
    range of values

-   added controlled values and documentation for mainLang attribute on
    textLang element

-   changed the url attribute on the graphic element to accept a wider
    range of values

## Citation
Corpus Coranicum Project, ed. Michael Marx. TEI Data. Berlin-Brandenburg Academy of Sciences and Humanities. https://github.com/telota/corpus-coranicum-tei.

## Licence
© Berlin-Brandenburgische Akademie der Wissenschaften 2024
Creative Commons CC BY-SA 4.0 https://creativecommons.org/licenses/by-sa/4.0/

## Contact
* Michael Marx (marx@bbaw.de), Berlin-Brandenburgische Akademie der Wissenschaften
* TELOTA (telota@bbaw.de), Berlin-Brandenburgische Akademie der Wissenschaften
