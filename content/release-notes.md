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

* Some standard `concept_ids` are mapped to the wrong domains. Currently, source-to-domain mappings are based on the domain of the source `concept_id`. This means where a source concept maps to multiple standard concepts in different domains, or where a concept has been remapped from one domain to another, the standard `concept_id` lands in the incorrect table. Mostly affecting `condition_occurrence` (~0.5% concepts), `observation` (~0.7% concepts) and `procedure_occurrence` (~7% concepts). A fix is planned for v2.0.0
* Some `gender_concept_ids` are mapped to non-standard codes
* Ethnicity and race concepts are not yet correctly mapped. We would advise that these are not used. A fix is planned in a future minor release.
* `procedure_occurrence.modifier_concept_id` is not mapped.
* A small number of `observation` (~0.002%) and `procedure_occurrence` (~0.02%) records are occurring outside of valid visit date periods.
* A small number of `observation` (~0.001%) and `procedure_occurrence` (~0.007%) records are not linked to a valid `care_site`. Some of these are due to `visit_occurrence` records not being linked to a valid `care_site` (n=2) but mostly these are referencing a non-existent `visit_occurrence_id`.
* A certain amount of duplication of records with respect to `person_id` + `concept_id` + `date` exists in the clinical data. 
    * Typically this occurs in GP source data, and typically affects <1% of records within a given `care_site`.
    * In some cases secondary care sources are affected and this may be related to the fact that spell/episode structure is not yet fully represented in the `visit_occurrence` and `visit_detail` objects. A fix is planned for v2.0.0

### Flexible Data Model

* not included in this release

