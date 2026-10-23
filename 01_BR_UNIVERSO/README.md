# Brazilian Population Census 2022
## Integrated National Dataset of Census Tract Aggregates

### Overview

This dataset integrates publicly available census tract-level
aggregates from the Brazilian Population Census 2022, produced
by the Instituto Brasileiro de Geografia e Estatística (IBGE).

The integrated database was prepared to support reproducible
spatial analysis of demographic, socioeconomic, and
housing-related characteristics across Brazil.

This is a research-derived integration of official IBGE data,
not an official dataset published by IBGE.

### Dataset structure

- Geographic coverage: Brazil
- Reference year: 2022
- Spatial unit: Census tract (setor censitário)
- Number of records: 468,099
- Number of columns: 1,356
- Geographic identifier: CD_SETOR
- Data format: Apache Parquet

The database includes 29 identification and territorial
characterization fields, 9 basic statistical indicators,
and 1,318 thematic variables.

### Integrated sources

| Code | Dataset | Variables |
|---|---|---:|
| BASICO | Basic and territorial information | 38 columns |
| DOM1 | Household Characteristics - Part 1 | 89 |
| DOM2 | Household Characteristics - Part 2 | 406 |
| DOM3 | Household Characteristics - Part 3 | 148 |
| DEM | Demography | 36 |
| PAR | Household Relationships | 182 |
| COR | Color or Race | 95 |
| ALF | Literacy | 362 |

The listed variable counts for thematic datasets exclude
the common census tract identifier.

Mortality, Indigenous-specific, and Quilombola-specific
thematic datasets are not included in this release.

### Data processing

The processing workflow comprises:

1. Acquisition of official IBGE CSV archives.
2. Standardization of census tract identifiers.
3. Conversion of source datasets to Apache Parquet.
4. Preservation of thematic variable prefixes.
5. Integration using CD_SETOR as the unique key.
6. Preservation of all census tracts in the Basic dataset.
7. Consolidation of integration batches into a national file.
8. Validation against the processed source datasets.

The national database was integrated using a left join
strategy with the Basic dataset as the territorial reference.

### Data coverage and missing values

The Basic dataset contains 468,099 census tracts.

The thematic datasets contain 458,772 census tracts.
The remaining 9,327 census tracts are retained in the
integrated database, with null values in all thematic fields.

Original values were preserved as text during processing.
The statistical disclosure control marker X must not be
interpreted as zero or as a missing join value.

Numerical conversion, including treatment of decimal commas,
must be performed according to the requirements of each analysis.

### Validation

The integrated database was compared against the eight
processed Parquet source datasets.

Validation results:

- 1,355 data variables compared.
- Zero value discrepancies identified.
- 468,099 unique census tract records.
- 9,327 Basic-only census tracts verified.
- Zero non-null thematic values in those Basic-only tracts.

These checks establish consistency between the integrated
database and the processed source files. They do not
independently certify the accuracy of the original IBGE
statistics or all upstream processing decisions.

### Documentation files

- DICIONARIO_COMPLETO_2022.csv
- DICIONARIO_COMPLETO_2022.xlsx
- RELATORIO_VARIAVEIS_2022.csv
- RESUMO_VALIDACAO_2022.csv
- VALIDACAO_SETORES_EXCLUSIVOS_2022.csv

The integrated data dictionary includes variable identifiers,
source groups, thematic classifications, and descriptions.

The territorial field descriptions should be checked against
the corresponding IBGE methodological documentation before
final public release.

### Official data source

Instituto Brasileiro de Geografia e Estatística (IBGE).
Censo Demográfico 2022 - Agregados por Setores Censitários.

https://ftp.ibge.gov.br/Censos/Censo_Demografico_2022/Agregados_por_Setores_Censitarios/

### Reproducible workflow

The computational notebook is available at:

https://github.com/PriscilaForcel/DOUTORADO

The workflow was developed using Python and Google Colab,
with supporting libraries including Pandas, PyArrow,
and DuckDB.

### Research context

This database was prepared within doctoral research in
Urban Engineering at the Federal University of São Carlos
(UFSCar), Brazil.

Research funding: Fundação de Amparo à Pesquisa do Estado
de São Paulo (FAPESP), grant 2025/08490-4.

Related research context: Centro de Estudos da Favela
(CEFAVELA), FAPESP grant 2022/12259-8.

### Citation and license

The dataset DOI, formal citation, version, and distribution
license will be added following final repository preparation
and verification of source-data reuse conditions.
