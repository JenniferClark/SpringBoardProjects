# Smart School Finder
## A Data-Driven School Recommendation System for Bay Area Families

**Capstone Final Project Report**  
**Author:** Jennifer Clark  
**Program:** Data Science  
**Date:** January 2026

---

## Executive Summary

Choosing the right K–12 school is a high-impact decision for families, yet school information is fragmented across multiple public and private data sources, often inconsistent and difficult to compare. Existing school search tools frequently rely on a limited set of metrics, such as standardized test scores, which do not capture the full range of factors families care about.

This capstone project presents **Smart School Finder**, a data-driven school recommendation system designed to help families discover and compare schools in the Bay Area. The project integrates heterogeneous datasets, resolves duplicate school entities, engineers interpretable features, and applies a preference-weighted scoring framework to generate personalized school rankings.

The resulting system produces explainable, customizable recommendations and establishes a scalable foundation for future machine-learning-based enhancements.

---

## 1. Problem Statement

Families seeking K–12 schools must navigate information spread across multiple sources, each with different naming conventions, identifiers, and levels of data quality. Public and private school datasets are rarely integrated, leading to duplicate records and incomplete school profiles.

Key challenges include:
- Fragmented and inconsistent school data
- Lack of unified school identifiers
- Over-reliance on single metrics in existing tools
- Limited transparency in recommendation logic

**Research Question:**  
Can a unified, feature-rich school dataset support explainable and preference-driven school recommendations for families?

---

## 2. Data Sources

The system integrates data from the following sources:

| Dataset | Description |
|------|------------|
| NCES Common Core of Data (CCD) | Public school directory and attributes |
| Private School Survey (PSS) | Private school enrollment and grade coverage |
| California Private School Directory | State-level private school information |
| CAIS | Independent school enrichment and membership data |
| Program Lists | IB, Montessori, Waldorf, and other programs |
| Geocoding Services | Address normalization and geographic filtering |

Each dataset contributes complementary information but requires normalization and reconciliation before integration.

---

## 3. Methodology and System Architecture

### 3.1 Data Pipeline Overview

The project follows a modular, reproducible pipeline:

1. Raw data ingestion
2. Field standardization and cleaning
3. Canonical school ID creation
4. Multi-source entity resolution
5. Address and campus normalization
6. Feature engineering
7. Recommendation scoring

### 3.2 Canonical Data Model

The system uses a relational canonical data design:

- **schools_master:** One canonical row per school containing display fields and engineered features
- **schools_locations:** Multiple campus or address records per school
- **schools_source_links:** Traceable links to original source records

This architecture preserves data provenance while enabling clean downstream analysis.

---

## 4. Feature Engineering

Features were engineered to balance coverage, interpretability, and usefulness for families.

### Feature Categories

- **Grade Bands:** PK, Elementary, Middle, High
- **School Type:** Public, Private, Charter
- **Enrichment Programs:** IB, Montessori, Waldorf, Arts, Language Immersion
- **Geographic Features:** Bay Area regional filters, proximity measures
- **Data Quality Flags:** Address confidence and source coverage indicators

Binary feature flags were favored to improve transparency and future extensibility.

---

## 5. Recommendation Model

### Model Type

**Weighted Scoring Model (Rule-Based)**

### Rationale

The recommendation approach prioritizes:
- Explainability for end users
- Customizable preference weights
- Avoidance of black-box decision making

### Scoring Inputs

- Grade-level compatibility
- Enrichment program alignment
- Geographic proximity
- Data completeness and confidence

This framework allows users to adjust priorities and supports future integration of machine-learning ranking models.

---

## 6. Results and Findings

Key findings from the integrated dataset include:

- Canonical entity resolution significantly reduced duplicate school records
- Enrichment program coverage varies substantially between public and private schools
- Geographic filtering reduces the candidate school search space dramatically
- Core feature coverage exceeds 98% across the dataset

These results demonstrate the feasibility of scalable, data-driven school recommendations.

---

## 7. Limitations

- Absence of real user interaction or preference data
- Incomplete enrichment data for some private institutions
- No longitudinal outcome validation (e.g., enrollment success or student outcomes)

---

## 8. Recommendations for the Client

1. **Adopt preference-weighted rankings rather than fixed scores**  
   Enables families to tailor recommendations to their priorities.

2. **Expand enrichment program data collection**  
   Enrichment features provide meaningful differentiation beyond academic metrics.

3. **Introduce user feedback mechanisms**  
   Feedback data can support iterative improvement and future ML-based ranking models.

---

## 9. Future Work

Potential extensions of this project include:

- Collaborative filtering using parent behavior
- Natural language processing of school websites
- Longitudinal outcome tracking
- Specialized recommendation paths for special-needs families

---

