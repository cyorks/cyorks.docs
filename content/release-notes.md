---
title: Release notes
---

## Connected Yorkshire Data Release Notes

|    |    |
|----|----|
|Version|1.0.0|
|Release date|2020-11-02|


### Common Data Model (OMOP)

|    |    |
|----|----|
|CDM version|6.0.0|
|Vocabulary version|v6.0 10-SEP-2020|


_In this release_

* Limited to a random cut of up to 50,000 patients, this is not the full Connected Yorkshire population
* General Practice records covering Bradford and Airedale
* Bradford Teaching Hospitals NHS Foundation Trust patient records
* Airedale NHS Foundation Trust patient records

_Known issues_

* Some `gender_concept_ids` are mapped to non-standard codes
* Ethnicity and race concepts are not yet correctly mapped. We would advise that these are not used. A fix is planned in a future release.
* `procedure_occurrence.modifier_concept_id` is not mapped.
* A small number of `observation` (~0.0002%), `procedure_occurrence` (~0.001%) and `condition_occurrence` (~0.07%) records are occurring outside of valid visit date periods.
* A certain amount of duplication of records with respect to `person_id` + `concept_id` + `date` exists in the clinical data. 
    * Typically this occurs in GP source data, and typically affects <1% of records within a given `care_site`.
    * In some cases secondary care sources are affected and this may be related to the fact that spell/episode structure is not yet fully represented in the `visit_occurrence` and `visit_detail` objects. A fix is planned for a future release.

### Flexible Data Model

* not included in this release

