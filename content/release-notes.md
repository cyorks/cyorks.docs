---
title: Release notes
---

## Connected Yorkshire Data Release Notes

|    |    |
|----|----|
|Version|1.0.0|
|Release date|2020-08-14|


### Common Data Model (OMOP)

|    |    |
|----|----|
|CDM version|5.3.1|
|Vocabulary version|v5.0 03-APR-20|


_In this release_

* Limited to a random cut of up to 50,000 patients, this is not the full Connected Yorkshire population
* General Practice records covering Bradford and Airedale
* Bradford Teaching Hospitals NHS Foundation Trust patient records
* Airedale NHS Foundation Trust patient records

_Known issues_

* Some `concept_ids` are mapped to the wrong domains. Currently, source-to-domain mapping are based on the domain of the source `concept_id`. This means where a source concept maps to multiple standard concepts in different domains, or where a concept has been remapped from one domain to another, the standard `concept_id` lands in the incorrect table. Mostly affecting `condition_occurrence` (~0.5% concepts), `observation` (~0.7% concepts) and `procedure_occurrence` (~7% concepts). A fix is planned for v2.0.0
* Some `gender_concept_ids` are mapped to non-standard codes
* Ethnicity and race concepts are not yet correctly mapped. It is advised that these are not used. A fix is planned in a future release.


### Flexible Data Model

* not included in this release

