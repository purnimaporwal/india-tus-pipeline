# india-tus-pipeline

**Harmonisation and pipeline construction for India's Time Use Survey (TUS 2019)**

This repository documents my data harmonisation work on India's National Time Use Survey 2019, conducted as a Research Associate at the Institute of Development Studies (IDS), Jaipur, under the ICSSR-funded gender research project.

## Overview

The India TUS 2019 is a large-scale diary-based household survey covering time allocation across 146 activity categories, collected across all Indian states and union territories. The raw data is distributed across hierarchical text files at six levels: household, individual, activity, secondary activity, travel, and context variables.

This pipeline harmonises **10.6 million+ observations** from the raw hierarchical files into analysis-ready panel datasets for gender research on unpaid work and labour inequality.

## Data Structure

The TUS 2019 raw files use a fixed-width text format with variable dictionaries (`.dct` files). Key challenges include:

- Six-level hierarchical structure requiring sequential merge operations
- Inconsistent encoding across state-level files
- Activity classification using the National Classification of Activities for Time Use Studies (NCATUS) at the three-digit level
- Sampling weights varying by household size and geography

## Pipeline Components

```
raw/              Raw TUS text files (not included — available from MOSPI)
dct/              Dictionary files for variable extraction
code/
  01_extract.do   Extract variables from raw fixed-width files using .dct
  02_merge.do     Merge across six hierarchical levels
  03_clean.do     Harmonise activity codes, recode variables, apply weights
  04_summary.do   Produce weighted summary statistics and descriptive outputs
output/           Analysis-ready datasets (not included)
```

## Methods

- Stata do-file pipelines for reproducible extraction and merging
- Dictionary-based variable extraction from fixed-width raw files
- NCATUS activity code harmonisation for primary and secondary activities
- Application of household and individual sampling weights
- Outputs include: time use by activity category disaggregated by sex, employment status, household type (joint/nuclear), and state

## Status

Pipeline construction was completed in May 2025. Code is being cleaned for public sharing. Outputs contributed to:
- Two PRISMA-based systematic literature reviews on gendered time allocation and labour inequality (in preparation for journal submission, with M. Mahamallik, IDS Jaipur)
- Data cleaning contribution for India's TUS second round (2024)

The TUS pipeline work was also where my curiosity about what time-use data reveals and what it quietly misses first became concrete. Working inside the raw files showed me how much it depends on how activity boundaries are drawn.

## Data Access

Raw TUS 2019 data is available from the Ministry of Statistics and Programme Implementation (MOSPI), Government of India: [mospi.gov.in](https://mospi.gov.in)

## Contact

Purnima Porwal — porwal.purnima18@gmail.com
