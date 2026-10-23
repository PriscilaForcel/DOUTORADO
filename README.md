# Doutorado em Engenharia Urbana | Urban Engineering PhD Research

**Inteligência Artificial, análise espacial e necessidades habitacionais no Brasil**

Este repositório reúne códigos, procedimentos metodológicos, bases de dados derivadas, documentação e produtos científicos desenvolvidos no âmbito de uma pesquisa de doutorado no Programa de Pós-Graduação em Engenharia Urbana da Universidade Federal de São Carlos (PPGEU/UFSCar), com financiamento da Fundação de Amparo à Pesquisa do Estado de São Paulo (FAPESP).

A pesquisa investiga o potencial de técnicas interpretáveis de Aprendizado de Máquina para ampliar o detalhamento territorial das estimativas do déficit habitacional brasileiro. A proposta articula o desenvolvimento de métodos computacionais com uma reflexão crítica sobre os limites conceituais e operacionais da mensuração das necessidades habitacionais.

## Projeto de pesquisa

**Título:** Inteligência artificial aplicada à estimativa do déficit habitacional no Brasil: uma abordagem multiescalar de desagregação por setor censitário.

**Pesquisadora:** Priscila Kauana Barelli Forcel

**Instituição:** Universidade Federal de São Carlos (UFSCar)

**Programa:** Programa de Pós-Graduação em Engenharia Urbana (PPGEU)

**Financiamento:** Fundação de Amparo à Pesquisa do Estado de São Paulo (FAPESP) — Processo nº 2025/08490-4.

**Vinculação científica:** Centro de Estudos da Favela (CEFAVELA), associado ao processo FAPESP nº 2022/12259-8.

## Problema de pesquisa

A mensuração do déficit habitacional constitui um instrumento importante para o diagnóstico e o planejamento das políticas habitacionais brasileiras. Entretanto, suas categorias e escalas de divulgação apresentam limitações para representar a diversidade das necessidades de moradia e as desigualdades existentes no território.

A metodologia da Fundação João Pinheiro (FJP) constitui a principal referência nacional para o cálculo do déficit habitacional. Sua aplicação aos microdados censitários permite produzir estimativas territorializadas, mas a escala das Áreas de Ponderação (APs) pode ocultar diferenças importantes entre setores de um mesmo município.

O projeto investiga como técnicas de Aprendizado de Máquina supervisionado, associadas a dados censitários e fontes complementares, podem contribuir para a desagregação espacial dessas estimativas, preservando a interpretabilidade dos resultados e reconhecendo os limites da quantificação das necessidades habitacionais.

## Objetivo geral

Desenvolver e aplicar um modelo interpretável de Aprendizado de Máquina supervisionado para desagregar o déficit habitacional brasileiro das Áreas de Ponderação para os setores censitários, analisar sua distribuição espacial e investigar os fatores sociodemográficos associados, a fim de ampliar o detalhamento territorial dos diagnósticos e seu potencial de apoio às políticas públicas.

## Objetivos específicos

- Analisar criticamente os limites conceituais e metodológicos da mensuração do déficit habitacional no Brasil, com referência à metodologia da Fundação João Pinheiro.
- Calcular e mapear o déficit habitacional por Área de Ponderação, a partir dos microdados da amostra do Censo Demográfico 2022 e das adaptações metodológicas necessárias.
- Construir bases integradas de variáveis censitárias e, quando pertinente, fontes complementares para a modelagem territorial.
- Investigar e comparar técnicas de Aprendizado de Máquina supervisionado, considerando desempenho, capacidade de generalização e interpretabilidade.
- Desenvolver e validar estimativas espacialmente desagregadas para os setores censitários brasileiros.
- Investigar a associação entre o déficit habitacional e características sociodemográficas, com atenção às desigualdades de gênero, raça/cor, arranjos familiares e condições socioeconômicas.
- Avaliar criticamente a suficiência dos dados disponíveis para representar as necessidades habitacionais.
- Disponibilizar bases, códigos, documentação e resultados da pesquisa em formatos acessíveis e reproduzíveis, respeitadas as condições de uso das fontes originais.

## Estratégia metodológica

O projeto aprovado pela FAPESP está organizado em seis etapas de investigação.

| Etapa | Descrição |
|---|---|
| **1. Cálculo do déficit habitacional** | Construção das estimativas por Área de Ponderação, com base na metodologia da FJP e nos microdados da amostra do Censo 2022. |
| **2. Estruturação dos dados** | Integração de bases, pré-processamento, análise de correlação, investigação da multicolinearidade e avaliação de redução de dimensionalidade. |
| **3. Modelagem supervisionada** | Experimentação com algoritmos de regressão e Aprendizado de Máquina, considerando desempenho e interpretabilidade. |
| **4. Desagregação e validação espacial** | Aplicação dos modelos aos setores censitários, comparação com referências agregadas e avaliação dos padrões espaciais dos erros. |
| **5. Avaliação crítica e interpretação** | Investigação das limitações dos dados e das associações com características sociodemográficas e territoriais. |
| **6. Disseminação dos resultados** | Disponibilização de bases de dados, documentação, códigos e produtos para pesquisa e planejamento habitacional. |

As etapas representam o plano metodológico da pesquisa. Sua inclusão neste README não significa que todas já estejam concluídas.

## Fontes de dados

A pesquisa considera principalmente:

- **Censo Demográfico 2022 — Microdados da Amostra:** referência para a construção de estimativas do déficit habitacional por Área de Ponderação, conforme a disponibilidade de variáveis e as adaptações metodológicas necessárias.
- **Censo Demográfico 2022 — Resultados do Universo:** fonte de informações demográficas, domiciliares e territoriais agregadas por setor censitário.
- **Malhas territoriais do IBGE:** referência para análises espaciais e compatibilização de unidades geográficas.
- **Cadastro Único (CadÚnico):** fonte administrativa complementar, sujeita a condições de acesso, cobertura, qualidade e proteção das informações.
- **Outras bases complementares:** registros administrativos, dados territoriais e fontes de sensoriamento remoto, conforme sua pertinência metodológica.

A integração dessas fontes será orientada pela compatibilidade territorial, temporal e conceitual dos indicadores.

## Projetos e bases de dados

### 01 — Censo Demográfico 2022: Universo

**Status:** Banco nacional integrado e validado, versão 1.0.0, disponibilizado no Zenodo.

Este projeto reúne os agregados por setores censitários do Censo Demográfico 2022, produzidos pelo Instituto Brasileiro de Geografia e Estatística (IBGE), em um único banco nacional.

O conjunto integrado apresenta:

- **468.099 setores censitários** de todo o Brasil.
- **1.356 colunas**, incluindo identificadores territoriais e variáveis temáticas.
- Dados básicos, características dos domicílios, demografia, parentesco, cor ou raça e alfabetização.
- Dicionário integrado das variáveis e relatórios de validação.

As verificações realizadas não identificaram divergências entre os valores do banco integrado e os arquivos Parquet tratados utilizados como fontes.

O conjunto constitui uma etapa de preparação de dados para análises posteriores. Não representa, isoladamente, estimativas do déficit habitacional por setor censitário.

**Base de dados no Zenodo:** https://doi.org/10.5281/zenodo.23599214

**Código e documentação:** [01_BR_UNIVERSO](./01_BR_UNIVERSO/)

Novos projetos, procedimentos de análise e produtos científicos poderão ser adicionados a este repositório conforme o desenvolvimento da pesquisa.

## Métodos e ferramentas computacionais

As ferramentas e técnicas utilizadas ou previstas incluem:

**Processamento e integração de dados**
- Python e Google Colab.
- Pandas, PyArrow e DuckDB.
- Arquivos CSV, Excel e Apache Parquet.

**Análise estatística e preparação para modelagem**
- Estatística descritiva e análise de correlação.
- Identificação de multicolinearidade.
- Seleção de variáveis e, quando pertinente, Análise de Componentes Principais (ACP).

**Aprendizado de Máquina e interpretabilidade**
- Modelos lineares e regressões penalizadas.
- Modelos baseados em árvores e métodos de ensemble.
- Redes Neurais Artificiais.
- Técnicas de interpretabilidade, como SHAP e LIME.

**Avaliação e análise espacial**
- Métricas de desempenho, incluindo R², RMSE e MAE.
- Validação cruzada e comparação multiescalar.
- Análise espacial dos resíduos e avaliação da heterogeneidade territorial.

A seleção das técnicas dependerá dos experimentos e das avaliações metodológicas realizados durante o doutorado.

## Ciência aberta e reprodutibilidade

A pesquisa busca promover transparência, rastreabilidade metodológica e reutilização responsável de dados e procedimentos computacionais.

Os produtos são organizados por projeto, acompanhados, quando aplicável, de documentação das fontes, código de processamento, dicionários de dados, relatórios de validação e informações sobre suas limitações.

Os conjuntos de dados concluídos poderão ser depositados em repositórios científicos com identificadores persistentes (DOI), como o Zenodo.

A disponibilização de produtos derivados respeitará as condições aplicáveis às fontes originais e os requisitos de proteção de dados.

## Autoria e contato

**Priscila Kauana Barelli Forcel**

Programa de Pós-Graduação em Engenharia Urbana — Universidade Federal de São Carlos (UFSCar)

ORCID: https://orcid.org/0000-0002-1321-4716

## Financiamento e vinculação científica

Esta pesquisa recebe apoio da **Fundação de Amparo à Pesquisa do Estado de São Paulo (FAPESP)**, por meio da bolsa de doutorado vinculada ao processo **2025/08490-4**.

A investigação articula-se à agenda metodológica do **Centro de Estudos da Favela (CEFAVELA)**, associado ao processo FAPESP **2022/12259-8**, especialmente às discussões sobre estimativas territorializadas, integração de dados e necessidades habitacionais.

As opiniões, hipóteses e conclusões expressas nos produtos são de responsabilidade de seus autores e não necessariamente refletem a visão da FAPESP ou das instituições envolvidas.
