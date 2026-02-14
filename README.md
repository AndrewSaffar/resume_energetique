# ESG Climate Report Extraction Agent

## Overview

This project implements a lightweight LLM-based pipeline to
automatically extract structured climate and ESG information from energy
sector sustainability reports.

The system transforms unstructured narrative documents (PDF reports)
into structured, machine-readable JSON suitable for downstream
analytical use.

The goal is to explore how large language models can support automated
climate intelligence workflows in energy organizations.

------------------------------------------------------------------------

## Problem Statement

Energy and utility companies publish long ESG and sustainability reports
containing:

-   Climate commitments\
-   Emissions reduction targets\
-   Scope 1/2/3 indicators\
-   Renewable project descriptions\
-   Transition investments\
-   Climate risk disclosures

These documents are rich in information but difficult to process
automatically.

This project investigates how an LLM-based agent can:

1.  Summarize complex reports\
2.  Extract structured climate-relevant information\
3.  Validate internal consistency\
4.  Reduce hallucination risk through rule-based checks

------------------------------------------------------------------------

## System Architecture

PDF Report → Text Extraction → Structured Summary (LLM) → Structured ESG
Extraction (LLM) → Validation Layer → Final JSON Output

------------------------------------------------------------------------

## Validation Strategy

-   JSON schema conformity\
-   Type checking\
-   Chronological consistency checks\
-   Numerical range validation\
-   Source excerpt traceability

------------------------------------------------------------------------

## Limitations

-   Partial reliance on LLM-based validation\
-   No retrieval-augmented generation (RAG)\
-   No quantitative benchmark evaluation

------------------------------------------------------------------------

## Design Philosophy

This project prioritizes:

-   Structured data over narrative summaries\
-   Modularity over complexity\
-   Validation over blind trust in model outputs\
-   Practical applicability in energy-sector workflows

## Reproducibility

To run this code yourself, first clone this repo.
Then run:
```
conda env create -f environment.yml
conda activate conda_env
```

You will also need to create an API key on https://aistudio.google.com/ and add it to a .env file under:
`GEMINI_API_KEY = <YOUR_API_KEY>` 

Bear in mind LLMs are non-deterministic, so results will vary from one run to another.

## Data

The example report used for development is publicly available on the company's official website.

Due to copyright considerations, the PDF is not included in this repository.

Users may download any public ESG report and place it in the `/documents` folder.

Note: Example outputs shown in this repository use anonymized company names.
The pipeline is designed to be report-agnostic.