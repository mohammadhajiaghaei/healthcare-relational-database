# Healthcare Relational Database (SQL)

**A normalised relational database for a healthcare setting — schema design,
constraints, and relationships modelled in SQL.**

MSc Data Science coursework — Data Repositories / database design.

---

## Overview

A relational database modelling patients, doctors, visits, and treatments in a
healthcare context. The focus is on clean schema design: normalisation, referential
integrity, constraints, and correctly modelled relationships (including subtype tables
and a many-to-many link).

## Schema design

- **Core entities:** `Patient`, `Doctor`, `Visit`, `Treatment`, `Address`, `Calendar`.
- **Subtype modelling:** `Treatment` is specialised into `Medication` and `Surgery`
  (shared primary key), so treatment-specific attributes live in the right place.
- **Many-to-many:** `SurgeryStaff` is a junction table linking surgeries to surgical
  staff.
- **Supporting entities:** `InsurancePolicy`, `SurgicalStaff`.

Design features:
- Primary and foreign keys throughout, with `PRAGMA foreign_keys = ON`.
- `CHECK` constraints to enforce valid values (e.g. `gender IN ('M','F','O')`,
  `treatment_type IN ('medication','surgery')`).
- A `Calendar` table to support time-based analysis of visits and treatments.

## What's in the notebook

- Full `CREATE TABLE` DDL for the schema.
- Sample (synthetic) records inserted to demonstrate the relationships working.
- Example queries joining across tables and listing table contents with pandas.

## Stack

SQLite · Python · pandas (developed in Google Colab).

## Note

Coursework project. All data in the notebook is synthetic sample data created to
demonstrate the schema — it does not represent any real individuals.
