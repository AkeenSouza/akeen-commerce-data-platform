# 03 - Roadmap

# Roadmap de Desenvolvimento

## Objetivo

Este documento define o planejamento evolutivo da **Akeen Commerce Data Platform (ACDP)**.

O projeto será desenvolvido de forma incremental, permitindo a construção gradual da plataforma e o aprendizado contínuo dos conceitos de Engenharia de Dados.

Cada fase possui objetivos claros, entregas esperadas e tecnologias específicas.

Ao final do roadmap, a plataforma deverá representar um ambiente moderno de dados, capaz de suportar ingestão, processamento, analytics, visualização e aplicações de Inteligência Artificial.

---

# Visão Geral

| Fase | Nome | Status |
|-------|------|--------|
| 01 | Fundação da Plataforma | ⏳ Planejado |
| 02 | Ingestão de Dados | ⏳ Planejado |
| 03 | Data Lake e Delta Lake | ⏳ Planejado |
| 04 | Processamento com Spark | ⏳ Planejado |
| 05 | Analytics Engineering | ⏳ Planejado |
| 06 | Business Intelligence | ⏳ Planejado |
| 07 | Data Quality e Observabilidade | ⏳ Planejado |
| 08 | DataOps e CI/CD | ⏳ Planejado |
| 09 | Inteligência Artificial | ⏳ Planejado |
| 10 | Evoluções Futuras | ⏳ Planejado |

---

# Fase 01 — Fundação da Plataforma

## Objetivo

Criar toda a estrutura inicial do projeto.

Nesta fase será construída a base que sustentará toda a evolução da plataforma.

## Entregas

- Estrutura do repositório
- Organização das pastas
- Documentação inicial
- Configuração do Git
- Configuração do GitHub
- Configuração do VS Code
- Definição dos padrões do projeto

## Tecnologias

- Git
- GitHub
- VS Code
- Markdown

## Conceitos Aprendidos

- Organização de projetos
- Versionamento
- Documentação
- Boas práticas de Engenharia de Software

---

# Fase 02 — Ingestão de Dados

## Objetivo

Construir pipelines responsáveis pela coleta de dados de diferentes fontes.

## Fontes previstas

- APIs REST
- CSV
- JSON
- Excel
- Datasets públicos
- Kaggle

## Entregas

- Scripts de ingestão
- Download automatizado
- Persistência no Data Lake
- Controle de logs

## Tecnologias

- Python
- Requests
- Pandas
- AWS S3

## Conceitos Aprendidos

- ETL
- ELT
- Ingestão
- Estruturação de pipelines

---

# Fase 03 — Data Lake e Delta Lake

## Objetivo

Implementar o armazenamento da plataforma utilizando arquitetura Lakehouse.

## Entregas

- Estrutura do Data Lake
- Camada Bronze
- Conversão para Delta Lake
- Organização das zonas do Data Lake

## Tecnologias

- AWS S3
- Delta Lake
- Databricks

## Conceitos Aprendidos

- Lakehouse
- Medallion Architecture
- ACID
- Versionamento de dados
- Time Travel

---

# Fase 04 — Processamento com Apache Spark

## Objetivo

Transformar os dados da camada Bronze em dados confiáveis na camada Silver.

## Entregas

- Limpeza
- Deduplicação
- Tratamento de tipos
- Normalização
- Enriquecimento

## Tecnologias

- Apache Spark
- PySpark
- Spark SQL
- Databricks

## Conceitos Aprendidos

- Processamento distribuído
- DataFrames
- Transformações
- Performance
- Particionamento

---

# Fase 05 — Analytics Engineering

## Objetivo

Construir a camada Gold utilizando dbt.

## Entregas

- Modelagem dimensional
- Tabelas Fato
- Dimensões
- Testes
- Documentação automática
- Data Lineage

## Tecnologias

- dbt Core
- SQL

## Conceitos Aprendidos

- Analytics Engineering
- Star Schema
- Modelagem Dimensional
- Incremental Models
- Snapshots

---

# Fase 06 — Business Intelligence

## Objetivo

Disponibilizar os dados para consumo analítico.

## Entregas

- Dashboards
- KPIs
- Indicadores
- Relatórios

## Tecnologias

- Power BI

## Conceitos Aprendidos

- Modelagem Analítica
- Visualização
- KPIs
- Storytelling com Dados

---

# Fase 07 — Data Quality e Observabilidade

## Objetivo

Garantir qualidade e confiabilidade da plataforma.

## Entregas

- Testes automatizados
- Monitoramento
- Logs
- Auditoria
- Alertas

## Tecnologias

- dbt Tests
- Logging
- Great Expectations (opcional)

## Conceitos Aprendidos

- Data Quality
- Observabilidade
- Governança
- Confiabilidade

---

# Fase 08 — DataOps e CI/CD

## Objetivo

Automatizar o ciclo de desenvolvimento da plataforma.

## Entregas

- GitHub Actions
- Deploy automatizado
- Execução automática de testes
- Padronização do fluxo de desenvolvimento

## Tecnologias

- GitHub Actions
- Git

## Conceitos Aprendidos

- CI/CD
- DataOps
- DevOps
- Automação

---

# Fase 09 — Inteligência Artificial

## Objetivo

Permitir consultas inteligentes sobre os dados da plataforma.

## Entregas

- Assistente em linguagem natural
- Geração automática de SQL
- Respostas baseadas na camada Gold

## Tecnologias

- LLM
- Python
- APIs

## Conceitos Aprendidos

- IA aplicada a Dados
- Text-to-SQL
- Agentes
- Engenharia de Prompt

---

# Fase 10 — Evoluções Futuras

Esta fase representa funcionalidades que poderão ser incorporadas conforme a evolução da plataforma.

Possíveis implementações:

- Apache Airflow
- Kafka
- Docker
- Terraform
- Kubernetes
- Unity Catalog
- Feature Store
- Machine Learning
- MLOps
- Data Contracts
- Streaming
- Catálogo de Dados
- APIs para consumo externo

---

# Critérios de Conclusão

Cada fase será considerada concluída quando atender aos seguintes critérios:

- Documentação atualizada.
- Código versionado.
- Estrutura organizada.
- Testes executados (quando aplicável).
- Funcionalidade validada.
- Registro das decisões arquiteturais (ADR).

---

# Filosofia de Desenvolvimento

O projeto seguirá uma abordagem iterativa.

Cada fase deverá gerar uma plataforma funcional, ainda que incompleta.

A prioridade será compreender profundamente os conceitos antes de avançar para tecnologias mais complexas.

Sempre que uma nova funcionalidade for implementada, deverão ser avaliados:

- Impactos arquiteturais.
- Escalabilidade.
- Performance.
- Facilidade de manutenção.
- Reutilização.
- Custos operacionais.

---

# Acompanhamento

Ao longo do projeto, este roadmap será atualizado para refletir:

- Novas funcionalidades.
- Mudanças de arquitetura.
- Tecnologias incorporadas.
- Melhorias identificadas durante o desenvolvimento.

O roadmap é um documento vivo e deverá evoluir junto com a plataforma.