# IT Labour Market Demand & Specialization Analysis

[Português](#português) · [English](#english)

<a name="english"></a>

## English

### Overview

This repository contains an end-to-end data science project for analyzing demand, specialization, and labor-market dynamics in the Brazilian Information Technology (IT) sector.

The project was organized as a reproducible analytical archive: raw and curated data, data dictionaries, ETL notebooks, analytical notebooks, visual outputs, data models, and final reports are kept together so that the work can be inspected, reused, and extended.

### Objectives

- Measure the demand for IT occupations across time, Brazilian states, economic subsectors, and legal-nature categories.
- Identify the IT specializations and subsectors with the strongest presence and growth.
- Compare public and private organizations where the available classification permits.
- Calculate labor-market indicators such as admissions, dismissals, employment balance, remuneration, and compound annual growth rate (CAGR).
- Produce analytical datasets and communication-ready deliverables for decision-making, research, and future updates.

### Analytical questions

- Where is IT employment concentrated in Brazil?
- Which IT occupations and specializations show the greatest demand?
- Which subsectors are expanding or contracting?
- How do demand and specialization vary by state and legal nature?
- How are remuneration ranges distributed across subsectors?

### Technologies and tools

- **Python** — primary programming language for data preparation, transformation, analysis, and notebook-based workflows.
- **Pandas** — tabular data manipulation, aggregation, cleaning, and generation of analytical datasets.
- **Scikit-learn** — analytical and machine-learning utilities used where applicable for data preparation and modeling support.
- **Seaborn** — statistical visualization and exploratory analysis of labor-market indicators.
- **Looker Studio** — dashboarding and interactive communication of the curated analytical outputs.
- **Jupyter Notebook** — execution and documentation of the ETL and analysis pipeline.
- **Excel/CSV** — exchange, inspection, and delivery formats for datasets and reference tables.

### Data and sources

The project uses structured Brazilian labor-market and classification data, together with supporting reference tables. The repository includes RAIS data dictionaries, municipality and legal-nature directories, IT occupation mappings, and derived analytical tables prepared for visualization and reporting.

The main data assets include:

- IT vacancy-demand and employment datasets.
- Aggregations by Brazilian state (`UF`).
- Aggregations by economic subsector.
- Aggregations by legal nature.
- CAGR and growth datasets.
- IT occupation and specialization mappings.
- Municipality and legal-nature lookup tables.
- Salary outlier extracts and visual summaries.

> **Data note:** The files stored in `data/` are analytical/curated outputs used by the project and are not a substitute for the original official source. Check the data dictionaries and the technical documentation before interpreting a field or reproducing a result.

### Methodology

The workflow follows an ETL and analytical-pipeline structure:

1. **Extract** source tables and reference data.
2. **Transform** occupation classifications, geographic identifiers, subsectors, legal-nature categories, and time dimensions.
3. **Validate and clean** records, standardize labels, handle analytical filters, and prepare consistent measures.
4. **Aggregate** the data by occupation, specialization, subsector, state, legal nature, and period.
5. **Measure** demand, employment balance, remuneration, distributions, and growth.
6. **Analyze** concentration, specialization, comparisons, and outliers.
7. **Deliver** curated spreadsheets, notebooks, diagrams, dashboards-ready tables, and final reports.

The employment-balance concept used in the analysis is based on the relationship between admissions and dismissals:

\[
\text{Employment balance} = \text{Admissions} - \text{Dismissals}
\]

For a period with initial value \(V_0\), final value \(V_t\), and elapsed time \(t\), CAGR is calculated as:

\[
\text{CAGR} = \left(\frac{V_t}{V_0}\right)^{1/t} - 1
\]

The precise filters, mappings, transformations, and assumptions are documented in the notebooks and technical reports.

### Repository structure

```text
.
├── data/       # Curated analytical datasets and visualization-ready spreadsheets
├── doc/        # Data dictionaries, classifications, mappings, and ETL support files
├── nb/         # ETL, demand-metric, and CAGR analysis notebooks
├── reports/    # Final reports, presentations, diagrams, charts, and extracts
└── README.md   # Project documentation
```

### Main notebooks

- `nb/ETL_1.ipynb`: first ETL stage and preparation of source data.
- `nb/ETL-2.ipynb`: second ETL stage and analytical transformations.
- `nb/ETL-3.ipynb`: third ETL stage and consolidation of derived data.
- `nb/nb_metrica_demanda.ipynb`: demand metrics and related indicators.
- `nb/nb_metrica_demanda_CAGR.ipynb`: growth and CAGR analysis.

Notebook names reflect the project workflow; execute them in dependency order when rebuilding the pipeline.

### Reports and deliverables

The `reports/` directory contains the final project materials, including:

- Final analytical report in PDF.
- Technical documentation in PDF and DOCX.
- ETL presentation and project presentation.
- Entity-relationship models for the ETL stages.
- CAGR metric flowchart.
- Formula illustration for the employment-balance metric.
- Charts covering IT-worker distribution and salary ranges by subsector.
- Salary outlier extracts in CSV and XLSX formats.

The `doc/` directory complements these deliverables with data dictionaries, mappings, municipal directories, legal-nature references, and filtering notes.

### Reproducing the analysis

1. Clone the repository.
2. Install a Python environment with Jupyter and the libraries imported by the notebooks.
3. Open the notebooks under `nb/`.
4. Read the technical documentation and data dictionaries before execution.
5. Run the ETL notebooks in order: `ETL_1.ipynb`, `ETL-2.ipynb`, and `ETL-3.ipynb`.
6. Run `nb_metrica_demanda.ipynb` and then `nb_metrica_demanda_CAGR.ipynb`.
7. Compare regenerated outputs with the curated files in `data/` and the artifacts in `reports/`.

Because the repository does not currently include a pinned dependency file, the exact package versions should be recorded before a production rerun. For a stronger reproducibility setup, add a `requirements.txt` or `environment.yml` and pin the source-data version and execution date.

### Interpretation and limitations

- The results depend on the source period, occupation mapping, geographic standardization, and filters applied in the ETL process.
- A high number of records or admissions does not necessarily represent a shortage of qualified professionals.
- CAGR can be unstable when the initial value is very small or zero; interpret it together with absolute counts.
- Salary comparisons may be affected by outliers, missing values, inflation, contract type, workload, and regional cost differences.
- Public/private comparisons depend on the legal-nature classification and should not be generalized beyond the defined filters.
- The curated spreadsheets are analytical outputs; they should be refreshed when the source data or classification rules change.

### Recommended next steps

- Add a pinned environment specification and an automated pipeline.
- Include explicit source-period metadata in every derived dataset.
- Add automated data-quality checks for duplicates, missing identifiers, invalid categories, and unexpected measure changes.
- Version the source data and publish a changelog for each refresh.
- Add interactive dashboards or a semantic layer for recurring analysis.
- Extend the analysis with forecast models, regional specialization indices, and uncertainty or sensitivity analysis.

### Contribution and maintenance

Contributions are welcome. When extending the project:

- Preserve the separation between source/reference files, transformations, and final outputs.
- Document new fields, filters, mappings, and assumptions.
- Keep notebook execution order explicit.
- Avoid committing credentials or personal data.
- Validate generated tables against the corresponding source and report artifacts.

### License and attribution

No license is currently declared in the repository. Until a license is added, reuse and redistribution should be treated as restricted to the permissions granted by the copyright holder. Add a `LICENSE` file before accepting external contributions or distributing the datasets more broadly.

Project author and maintainer: **RosettiBR**.

---

<a name="português"></a>

## Português

### Visão geral

Este repositório contém um projeto completo de ciência de dados para analisar demanda, especialização e dinâmica do mercado de trabalho no setor de Tecnologia da Informação (TI) no Brasil.

O projeto foi organizado como um arquivo analítico reproduzível: dados brutos e tratados, dicionários de dados, notebooks de ETL, notebooks analíticos, visualizações, modelos de dados e relatórios finais permanecem juntos para que o trabalho possa ser auditado, reutilizado e expandido.

### Objetivos

- Medir a demanda por ocupações de TI ao longo do tempo, por estado brasileiro, subsetor econômico e natureza jurídica.
- Identificar as especializações e os subsetores de TI com maior presença e crescimento.
- Comparar organizações públicas e privadas quando a classificação disponível permitir.
- Calcular indicadores como admissões, desligamentos, saldo de vagas, remuneração e taxa composta de crescimento anual (CAGR).
- Produzir bases analíticas e entregáveis prontos para visualização, tomada de decisão, pesquisa e futuras atualizações.

### Perguntas analíticas

- Onde o emprego em TI está concentrado no Brasil?
- Quais ocupações e especializações apresentam maior demanda?
- Quais subsetores estão crescendo ou retraindo?
- Como demanda e especialização variam por estado e natureza jurídica?
- Como se distribuem as faixas de remuneração entre os subsetores?

### Tecnologias e ferramentas

- **Python** — linguagem principal para preparação, transformação, análise dos dados e execução dos notebooks.
- **Pandas** — manipulação tabular, agregação, limpeza e geração das bases analíticas.
- **Scikit-learn** — utilitários analíticos e de aprendizado de máquina utilizados, quando aplicável, no apoio à preparação e modelagem.
- **Seaborn** — visualização estatística e análise exploratória dos indicadores do mercado de trabalho.
- **Looker Studio** — criação de dashboards e comunicação interativa dos resultados tratados.
- **Jupyter Notebook** — execução e documentação do pipeline de ETL e análise.
- **Excel/CSV** — formatos de intercâmbio, inspeção e entrega das bases e tabelas de referência.

### Dados e fontes

O projeto utiliza dados estruturados do mercado de trabalho brasileiro e tabelas de classificação e apoio. O repositório inclui dicionários da RAIS, diretórios de municípios e naturezas jurídicas, mapeamentos de ocupações de TI e tabelas analíticas derivadas para visualização e elaboração dos relatórios.

Os principais ativos de dados incluem:

- Bases de demanda por vagas e emprego em TI.
- Agregações por unidade federativa (`UF`).
- Agregações por subsetor econômico.
- Agregações por natureza jurídica.
- Bases de CAGR e crescimento.
- Mapeamentos de ocupações e especializações em TI.
- Tabelas de municípios e naturezas jurídicas.
- Extrações de outliers salariais e resumos visuais.

> **Nota sobre os dados:** Os arquivos em `data/` são resultados analíticos/tratados utilizados pelo projeto e não substituem a fonte oficial original. Consulte os dicionários de dados e a documentação técnica antes de interpretar um campo ou reproduzir um resultado.

### Metodologia

O fluxo segue uma estrutura de ETL e análise:

1. **Extração** das tabelas de origem e dados de referência.
2. **Transformação** das classificações ocupacionais, identificadores geográficos, subsetores, naturezas jurídicas e dimensões temporais.
3. **Validação e limpeza** dos registros, padronização de rótulos, aplicação de filtros e preparação de medidas consistentes.
4. **Agregação** por ocupação, especialização, subsetor, estado, natureza jurídica e período.
5. **Medição** de demanda, saldo de emprego, remuneração, distribuições e crescimento.
6. **Análise** de concentração, especialização, comparações e outliers.
7. **Entrega** de planilhas tratadas, notebooks, diagramas, tabelas para visualização e relatórios finais.

O saldo de emprego utilizado na análise é baseado na relação entre admissões e desligamentos:

\[
\text{Saldo de emprego} = \text{Admissões} - \text{Desligamentos}
\]

Para um período com valor inicial \(V_0\), valor final \(V_t\) e tempo decorrido \(t\), o CAGR é calculado por:

\[
\text{CAGR} = \left(\frac{V_t}{V_0}\right)^{1/t} - 1
\]

Os filtros, mapeamentos, transformações e pressupostos específicos estão documentados nos notebooks e nos relatórios técnicos.

### Estrutura do repositório

```text
.
├── data/       # Bases analíticas tratadas e planilhas para visualização
├── doc/        # Dicionários, classificações, mapeamentos e arquivos de apoio ao ETL
├── nb/         # Notebooks de ETL, métricas de demanda e análise de CAGR
├── reports/    # Relatórios finais, apresentações, diagramas, gráficos e extrações
└── README.md   # Documentação do projeto
```

### Principais notebooks

- `nb/ETL_1.ipynb`: primeira etapa de ETL e preparação dos dados de origem.
- `nb/ETL-2.ipynb`: segunda etapa de ETL e transformações analíticas.
- `nb/ETL-3.ipynb`: terceira etapa de ETL e consolidação dos dados derivados.
- `nb/nb_metrica_demanda.ipynb`: métricas de demanda e indicadores relacionados.
- `nb/nb_metrica_demanda_CAGR.ipynb`: análise de crescimento e CAGR.

Os nomes refletem o fluxo do projeto; execute os notebooks na ordem de dependência para reconstruir o pipeline.

### Relatórios e entregáveis

A pasta `reports/` contém os materiais finais, incluindo:

- Relatório analítico final em PDF.
- Documentação técnica em PDF e DOCX.
- Apresentações de ETL e do projeto.
- Modelos entidade-relacionamento das etapas de ETL.
- Fluxograma da métrica CAGR.
- Ilustração da fórmula de saldo de emprego.
- Gráficos sobre distribuição de trabalhadores de TI e faixas salariais por subsetor.
- Extrações de outliers de remuneração em CSV e XLSX.

A pasta `doc/` complementa esses entregáveis com dicionários, mapeamentos, diretórios municipais, referências de natureza jurídica e notas sobre filtros.

### Reprodução da análise

1. Clone o repositório.
2. Configure um ambiente Python com Jupyter e as bibliotecas importadas pelos notebooks.
3. Abra os notebooks em `nb/`.
4. Leia a documentação técnica e os dicionários de dados antes da execução.
5. Execute os notebooks de ETL na ordem: `ETL_1.ipynb`, `ETL-2.ipynb` e `ETL-3.ipynb`.
6. Execute `nb_metrica_demanda.ipynb` e, depois, `nb_metrica_demanda_CAGR.ipynb`.
7. Compare os resultados regenerados com os arquivos tratados em `data/` e os artefatos em `reports/`.

Como o repositório ainda não possui um arquivo de dependências fixadas, as versões exatas dos pacotes devem ser registradas antes de uma nova execução de produção. Para fortalecer a reprodutibilidade, recomenda-se adicionar `requirements.txt` ou `environment.yml`, além da versão dos dados de origem e da data de execução.

### Interpretação e limitações

- Os resultados dependem do período da fonte, do mapeamento ocupacional, da padronização geográfica e dos filtros aplicados no ETL.
- Um número elevado de registros ou admissões não significa necessariamente escassez de profissionais qualificados.
- O CAGR pode ser instável quando o valor inicial é muito pequeno ou igual a zero; interprete-o junto com os valores absolutos.
- Comparações salariais podem ser afetadas por outliers, valores ausentes, inflação, tipo de contrato, jornada e diferenças no custo regional.
- Comparações entre setor público e privado dependem da classificação de natureza jurídica e não devem ser generalizadas além dos filtros definidos.
- As planilhas tratadas são resultados analíticos e devem ser atualizadas quando mudarem os dados de origem ou as regras de classificação.

### Próximos passos recomendados

- Adicionar especificação de ambiente fixada e pipeline automatizado.
- Incluir metadados explícitos do período de origem em cada base derivada.
- Criar verificações automáticas de qualidade para duplicidades, identificadores ausentes, categorias inválidas e variações inesperadas nas medidas.
- Versionar os dados de origem e publicar um changelog a cada atualização.
- Adicionar dashboards interativos ou uma camada semântica para análises recorrentes.
- Expandir o estudo com modelos de previsão, índices regionais de especialização e análises de incerteza ou sensibilidade.

### Contribuição e manutenção

Contribuições são bem-vindas. Ao ampliar o projeto:

- Preserve a separação entre arquivos de origem/referência, transformações e resultados finais.
- Documente novos campos, filtros, mapeamentos e pressupostos.
- Mantenha explícita a ordem de execução dos notebooks.
- Não inclua credenciais ou dados pessoais no repositório.
- Valide as tabelas geradas contra a fonte correspondente e os artefatos dos relatórios.

### Licença e atribuição

O repositório ainda não declara uma licença. Até que um arquivo `LICENSE` seja adicionado, o reúso e a redistribuição devem ser tratados como limitados às permissões concedidas pelo detentor dos direitos autorais. Adicione uma licença antes de aceitar contribuições externas ou distribuir amplamente as bases.

Autor e mantenedor do projeto: **RosettiBR**.
