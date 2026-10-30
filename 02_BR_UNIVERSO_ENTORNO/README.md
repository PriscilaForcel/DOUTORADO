# Brazilian Population Census 2022
## Integrated National Dataset of Census Tract Aggregates - Urban Environment Extension (V2)

### Overview

This dataset extends the Integrated National Dataset of Census Tract Aggregates from the Brazilian Population Census 2022 (V1) by incorporating the *Urban Environment Characteristics of Households* (*Características Urbanísticas do Entorno dos Domicílios*) dataset, published by the Instituto Brasileiro de Geografia e Estatística (IBGE).

The original database integrates eight thematic census datasets and provides a harmonized national structure for the analysis of demographic, socioeconomic, and housing-related characteristics at the census tract level.

Version 2.0.0 incorporates 35 additional variables related to urban environment characteristics, preserving the original census tract identifiers and all variables from Version 1.0.0.

This is a research-derived integration of official IBGE data. It is not an official integrated dataset published by IBGE.

**Version:** 2.0.0  
**Reference year:** 2022  
**Geographic coverage:** Brazil  
**Spatial unit:** Census tract (*setor censitário*)  
**Original dataset (V1):** https://doi.org/10.5281/zenodo.23599214  
**V2 DOI:** https://doi.org/10.5281/zenodo.23821338

---

### 1. Dataset structure

| Characteristic | Version 1.0.0 | Version 2.0.0 |
|---|---:|---:|
| Census tracts | 468,099 | 468,099 |
| Total columns | 1,356 | 1,391 |
| Additional urban environment variables | 0 | 35 |
| Census tracts matched with urban environment data | - | 340,965 |
| Census tracts without urban environment matches | - | 127,134 |
| Geographic identifier | `CD_SETOR` | `CD_SETOR` |
| Main format | Apache Parquet | Apache Parquet |

The main output file is:

`UNIVERSO_2022_NACIONAL_V2.parquet`

The 35 newly incorporated variables are named `ENT_V05000` through `ENT_V05034`.

All 468,099 census tracts from V1 are preserved in V2.

### 2. Data sources

The database combines the eight thematic datasets integrated in V1 with the urban environment dataset introduced in V2.

| Code | Dataset | Columns |
|---|---|---:|
| BASICO | Basic and territorial information | 38 |
| DOM1 | Household Characteristics - Part 1 | 89 |
| DOM2 | Household Characteristics - Part 2 | 406 |
| DOM3 | Household Characteristics - Part 3 | 148 |
| DEM | Demography | 36 |
| PAR | Household Relationships | 182 |
| COR | Color or Race | 95 |
| ALF | Literacy | 362 |
| ENT | Urban Environment Characteristics of Households | 35 |

The listed counts for the original eight datasets include the structure documented in V1. The common identifier `CD_SETOR` is counted only once in the integrated database.

**Official data provider:** Instituto Brasileiro de Geografia e Estatística (IBGE).

The original source datasets and methodological documentation are available through the IBGE Censo Demográfico 2022 dissemination platform.

### 3. Data integration methodology

The V2 database was constructed using the published V1 national Parquet file as the territorial reference.

The processing workflow includes:

1. Acquisition of the official IBGE urban environment data and dictionaries.
2. Loading the national urban environment CSV archive without extracting the original ZIP.
3. Standardization of the census tract identifier from `CD_setor` to `CD_SETOR`.
4. Identification of the 35 thematic variables, `V05000` to `V05034`.
5. Addition of the `ENT_` prefix to the new variables.
6. Validation of identifier uniqueness and territorial correspondence.
7. Integration with V1 using an exact-match `LEFT JOIN` on `CD_SETOR`.
8. Export of the integrated database in Apache Parquet format.
9. Validation of the original and newly incorporated variables.
10. Generation of consolidated dictionaries and technical documentation.

The `LEFT JOIN` operation preserves the complete geographic coverage of the original national database.

Original values are maintained as text to prevent unintended transformations of census identifiers, numerical representations and statistical disclosure markers.

### 4. Data coverage and missing values

The urban environment source dataset contains records for 340,965 census tracts.

The remaining 127,134 census tracts from V1 do not have corresponding records in the urban environment dataset. These records are retained in V2, with null values in all 35 newly incorporated variables.

**Important:** Missing values caused by an unmatched census tract must not be interpreted as the absence of urban infrastructure or as a zero value for an indicator.

Users must consult the IBGE methodological documentation and data dictionaries when interpreting individual variables.

### 5. Data validation

Two complementary audits were performed to assess the integrity of the integration.

**Preservation of V1 variables**

All 1,355 original data variables were compared between V1 and V2, using the census tract identifier as the matching key.

The comparison was conducted in 68 batches.

**Result: no discrepancies identified.**

**Validation of urban environment variables**

All 35 newly incorporated variables were compared against the original IBGE CSV records in four batches.

**Result: no discrepancies identified.**

Additionally, the validation confirmed that all 127,134 unmatched census tracts contain null values in the 35 new variables.

These procedures assess integration integrity and consistency with the source files. They do not constitute an independent validation of the official statistics produced by IBGE.

### 6. Repository organization

```text
02_BR_UNIVERSO_ENTORNO/
├── BR_UNIVERSO_DESENVOLVIMENTO.ipynb
├── README.md
├── DOCUMENTACAO/
│   ├── DICIONARIO_COMPLETO_2022_V2.csv
│   └── DICIONARIO_COMPLETO_2022_V2.xlsx
└── VALIDACAO/
    ├── RELATORIO_TECNICO_UNIVERSO_2022_V2.md
    └── RELATORIO_VALIDACAO_UNIVERSO_2022_V2.xlsx
```

**Processing notebook**

`BR_UNIVERSO_DESENVOLVIMENTO.ipynb` contains the Python workflow for downloading, preparing, integrating and validating the dataset.

**Documentation**

The `DOCUMENTACAO` directory contains the consolidated data dictionary in CSV and XLSX formats, covering all 1,391 columns.

**Validation**

The `VALIDACAO` directory contains the technical report and the Excel workbook documenting the integrity checks performed.

The national Parquet file is distributed through the [Version 2.0.0 Zenodo release](https://doi.org/10.5281/zenodo.23821338) rather than stored directly in GitHub.

### 7. Reproducibility

The processing notebook was developed using Python, Google Colab, DuckDB, Pandas and PyArrow.

The workflow includes acquisition routines for the original V1 dataset and official IBGE urban environment files, configurable working directories, integration procedures and validation checks.

The original database can be accessed through its version-specific Zenodo DOI:

https://doi.org/10.5281/zenodo.23599214

**Reproducibility status:** The original V2 output and its integration checks have been validated. A complete execution of the revised publication notebook in a clean environment remains to be verified.

### 8. Limitations

The database retains the coverage, concepts, classifications and disclosure restrictions of the official IBGE source datasets.

The urban environment component does not cover every census tract included in the original integrated database.

The data should not be interpreted without reference to the corresponding official documentation, and users should distinguish missing values from measured zero values.

This research-derived dataset facilitates integrated spatial analysis but does not replace the original IBGE publications.

### 9. Relationship with Version 1.0.0

Version 2.0.0 is an extension of the original national database. It does not change the original census tract coverage or the values of the 1,355 data variables incorporated in V1.

The V1 processing notebook and its documentation are available in the [`01_BR_UNIVERSO`](../01_BR_UNIVERSO/) directory.

The original Zenodo release remains accessible at:

https://doi.org/10.5281/zenodo.23599214

### 10. Citation and attribution

Please cite the corresponding Zenodo dataset record when using this database in research or other publications.

**Suggested citation (APA):**

Forcel, P. K. B. (2026). *Brazilian Population Census 2022: Integrated National Dataset of Census Tract Aggregates - Urban Environment Extension (V2)* (Version 2.0.0) [Dataset]. Zenodo. https://doi.org/10.5281/zenodo.23821338

**Original statistical data:** Instituto Brasileiro de Geografia e Estatística (IBGE), Censo Demográfico 2022.

**Research-derived integration and documentation:** Priscila Kauana Barelli Forcel.
