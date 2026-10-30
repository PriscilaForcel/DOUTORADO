# Relatório técnico de construção e validação
## Banco Nacional de Agregados por Setores Censitários — Censo 2022 (V2)

**Data de geração:** 30/10/2026

### 1. Objetivo

Documentar a incorporação dos agregados de Características
Urbanísticas do Entorno dos Domicílios à base nacional
de agregados por setores censitários do Censo 2022.

### 2. Fontes

- Instituto Brasileiro de Geografia e Estatística (IBGE).
- Censo Demográfico 2022 — agregados por setores censitários.
- Banco nacional original (V1).
- Características Urbanísticas do Entorno dos Domicílios.
- Dicionário oficial Entorno Domicílios.

### 3. Estrutura da integração

A integração foi realizada pela chave territorial CD_SETOR,
com correspondência exata entre os identificadores.

Foi utilizado LEFT JOIN, mantendo a totalidade dos setores
censitários presentes na base original.

As 35 variáveis incorporadas receberam prefixo ENT_,
preservando os códigos originais das variáveis do IBGE.

### 4. Resultados

- Setores censitários da V1: 468.099.
- Setores censitários da V2: 468.099.
- Colunas da V1: 1.356.
- Colunas da V2: 1.391.
- Variáveis de Entorno incorporadas: 35.
- Setores com correspondência no Entorno: 340.965.
- Setores sem correspondência no Entorno: 127.134.

### 5. Validação de integridade

Foram comparadas 1.355 variáveis originais entre V1 e V2,
em 68 lotes, com correspondência por CD_SETOR.

Resultado: nenhuma divergência.

As 35 variáveis de Entorno foram comparadas com o arquivo
CSV original do IBGE, em quatro lotes.

Resultado: nenhuma divergência.

Também foi confirmada a presença de valores nulos nas
35 variáveis de Entorno para os 127.134 setores sem
correspondência com o arquivo de origem.

### 6. Limitações

O banco V2 possui abrangência nacional, mas o conjunto
de Entorno não disponibiliza registros correspondentes
para todos os setores da base nacional.

A ausência de correspondência não deve ser interpretada
automaticamente como ausência de infraestrutura urbana.

A interpretação dos indicadores exige consulta às notas
metodológicas e aos dicionários do IBGE.

### 7. Arquivos de saída

- UNIVERSO_2022_NACIONAL_V2.parquet
- DICIONARIO_COMPLETO_2022_V2.csv
- DICIONARIO_COMPLETO_2022_V2.xlsx
- RELATORIO_VALIDACAO_UNIVERSO_2022_V2.xlsx

### 8. Situação

Integração e verificações de integridade concluídas.
A avaliação substantiva dos indicadores constitui etapa
posterior à validação dos arquivos.
