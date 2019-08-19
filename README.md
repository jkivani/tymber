# TYMBER
## Database on nominal number marking constructions

Jessica Katiuscia Ivani, Taras Zakharko

---

**Version 1.0.0-alpha**

---


**Table of Contents**

- [Overview](#introduction)
- [Data](#data)
- [Coverage map](#coverage-map)
- [License](#license)
- [How to cite](#how-to-cite)

# Overview

`Tymber` is a database on nominal marking that covers a stratified sample of currently approximately 250 languages worldwide. The database describes which nominal categories (nouns, pronouns, demonstratives as well as their subtypes) are contrastively marked in regards to number categories and which constructions are used to mark them. Only contrastively marked nominal categories are currently considered (e.g. if nouns don't show contrastive number marking, they are not considered to be marked for number). 

The database relies on autotypologizing method (Bickel & Nichols 2002) and is designed according to the principle of Late Aggregation: the data is collected and stored using a fine-grained, systematic descriptive model and is then aggregated as needed during subsequent data analysis. This design ensures that the data can be reused for a variety of purposes and no descriptive information is lost. 

As the internal database format is currently undergoing stabilization, only a subset of higher-level aggregations is currently published in this repository. This includes a list of attested number categories in languages, contrastive nominal categories and an overview of which types of constructions are used to mark number for a given nominal category in a language. 

# Data

The published data is currently available as four comma-separated tables in the folder `data`. The tables are the following ones:

- `nominal_number_categories.csv` describes which number categories are attested on nominals. There is one row per language in this table. The column `Glottocode` is the language glottocode. The columns `SG` (Singular),`SLT` (Singulative),`DU` (Dual),`TRI` (Trial),`QUA` (Quadral),`PAU` (Paucal),`PL` (Plural) contain `TRUE` if the respective number category is attested in the language and contrastively marked on nominals and `FALSE` otherwise. 


- `nominal_number_splits.csv` describes contrastive splits within number marking on nominal categories in respect to their semantic properties. There is one row per language in this table. The column `Glottocode` is the language glottocode. The columns `split.Pro.1.incl.excl` (clusivity contrast), `split.Pro.3.human` (human vs non-human third person pronoun contrast), `split.Pro.3.animate` (animate vs inanimate third person pronoun contrast), `split.DEM.human` (human vs non-human demonstrative pronoun contrast), `split.DEM.animate` (animate vs inanimate demonstrative pronoun contrast), `split.N.kin` (kinship terms contrast), `split.N.human` (human vs non-human nouns contrast), `split.N.animate` (animate vs inanimate nouns contrast) contain `TRUE` if the respective contrast is attested in the language in regards to at least one number marking category and `FALSE` otherwise


- `reference_types.csv` describes which groups of nominal categories are contrastive in regards to number marking. There are multiply rows per language in this table. The column `Glottocode` is the language glottocode. The column `NominalTypes` is a comma-separated list of nominal categories that show the same behavior in respect to nominal number marking, and contrastive behavior to all other groups in the same language. We refer to such groups as *reference types*.

- `nominal_number_construction_type.csv` describes which types of constructions are used to mark number on nominal categories in languages. There are multiple rows per language in this table. The column `Glottocode` is the language glottocode. The column `NumberCategory` is the number category and `NominalType` is the nominal category for which the nominal number constructions are considered. The rest of the columns, starting with `has.` (e.g. `has.suffix` or `has.tone`), contain `TRUE` is the respective construction type (e.g. a suffix marker or a tonal distinction) is used to mark the specific number category for the given nominal type in the given language in *at least one context*. The table does not distinguish how many such constructions may be present in the language or how complex are they. More detailed summary will be published in the future. 

# Coverage map

The file `maps/languages.html` is a standalone leaflet map that allows interactive exploration of the languages currently present in the sample. This map contains basic information about languages, attested nominal number categories as well as contrastive groups of nominal categories (reference types). You can download the file to your machine and then open it in your browser. Internet connection will be required. 

# License

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.


# How to cite

Ivani, Jessica & Zakharko, Taras. 2019. *Tymber, Database on nominal number marking constructions*. Version {version-number} [https://github.com/jivani/tymber/](https://github.com/jivani/tymber/)

Please make sure to always include the git commit id or the version number of the data you use in place of {version-number}. This ensures that results can be always reproduced even after the database has been updated. The GitHub website tracks all versions of the database that were ever published (you can switch between them by clicking on the branch menu on the top of this page and selecting an appropriate tag). `Tymber` uses [semantic versioning ](https://semver.org/spec/v2.0.0.html). 

# References

Bickel, Balthasar & Johanna Nichols. 2002. Autotypologizing databases and their use in fieldwork. In Peter Austin, Helen Dry & Peter Wittenburg (eds.), *Proceedings of the International LREC Workshop on Resources and Tools in Field Linguistics, Las Palmas,* 26-27 May 2002. Nijmegen: MPI for Psycholinguistics [[download](http://www.autotyp.uzh.ch/download/canary.pdf)].
