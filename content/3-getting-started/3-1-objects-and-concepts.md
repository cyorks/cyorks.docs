---
title: 3.1 Introduction to OMOP objects and concepts
---

# OMOP objects and concepts

OMOP is a Common Data Model adopted for the majority of the clinical data available via the Connected Yorkshire Data Platform. 

### Person

The `person` table holds a record for each person with clinical data in the model along with some basic demographic information.

### Observation period

The `observation_period` table defines a single period for each person during which it is possible that clinical data may be observed for that person.

### Visits

The `visits` table holds a record for every encounter that could lead to clinical data being entered into a patient's record. A single visit is linked to a single patient and a single care site.

### Clinical data

Clincal data is separated into different `domains` by the OMOP model, each held in a separate table. The main domains that we have populated with data are `condition_occurrence`, `device_exposure`, `drug_exposure`, `measurement`, `observation`, `procedure_occurrence`. Examples of how to query these different objects can be found in the section on [querying OMOP](./3-2-querying-omop).



