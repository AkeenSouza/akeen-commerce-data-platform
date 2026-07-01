# 04 - Stack Tecnológica

# Stack Tecnológica

## Objetivo

Este documento descreve todas as tecnologias utilizadas na **Akeen Commerce Data Platform (ACDP)**, bem como suas responsabilidades dentro da arquitetura.

A escolha das ferramentas foi baseada em três critérios principais:

- Alinhamento com o mercado de Engenharia de Dados.
- Potencial de aprendizado.
- Baixo custo para desenvolvimento de um ambiente pessoal.

A stack poderá evoluir ao longo do projeto conforme novas necessidades surgirem.

---

# Visão Geral

| Categoria | Tecnologia | Status |
|------------|------------|--------|
| IDE | Visual Studio Code | ✅ |
| Versionamento | Git | ✅ |
| Repositório | GitHub | ✅ |
| Linguagem | Python | ✅ |
| SQL | Spark SQL | ✅ |
| Cloud | AWS | ✅ |
| Data Lake | Amazon S3 | ✅ |
| Processamento | Databricks | ✅ |
| Engine | Apache Spark | ✅ |
| Storage | Delta Lake | ✅ |
| Analytics Engineering | dbt Core | ✅ |
| Visualização | Power BI | ✅ |
| Inteligência Artificial | LLM | 🔜 |
| CI/CD | GitHub Actions | 🔜 |
| Orquestração | Databricks Jobs | 🔜 |
| Data Quality | dbt Tests | 🔜 |

---

# Visual Studio Code

## Função

Principal ambiente de desenvolvimento do projeto.

Será utilizado para:

- Python
- SQL
- dbt
- Git
- Documentação
- Markdown

## Motivo da escolha

VS Code é atualmente uma das IDEs mais utilizadas por profissionais de Dados e possui excelente integração com Git, Python, dbt e extensões para desenvolvimento em nuvem.

---

# Git

## Função

Controlar todo o versionamento do projeto.

Será utilizado para:

- Commits
- Branches
- Merge
- Pull Requests
- Histórico de alterações

## Fluxo esperado

```
main

↓

develop

↓

feature/*
```

---

# GitHub

## Função

Hospedar o repositório do projeto.

Também será utilizado futuramente para:

- CI/CD
- Code Review
- Issues
- Documentação
- Releases

---

# Python

## Função

Linguagem principal da plataforma.

Será utilizada para:

- Ingestão de dados
- Automações
- APIs
- Scripts auxiliares
- IA

## Motivo da escolha

Python é a linguagem dominante na Engenharia de Dados moderna e possui excelente integração com Spark, Databricks, IA e bibliotecas de dados.

---

# SQL

## Função

Linguagem principal para manipulação dos dados.

Será utilizada em:

- Spark SQL
- dbt
- Power BI

Grande parte das regras de negócio será escrita utilizando SQL.

---

# AWS

## Função

Provedor de nuvem da plataforma.

Inicialmente serão utilizados apenas os serviços necessários para manter o projeto simples e econômico.

Possíveis serviços:

- Amazon S3
- IAM
- CloudWatch (futuro)

## Motivo da escolha

O autor já possui experiência profissional utilizando AWS, tornando o aprendizado mais focado nas tecnologias de Engenharia de Dados.

---

# Amazon S3

## Função

Armazenar todos os dados da plataforma.

Será utilizado como Data Lake.

Estrutura prevista:

```
raw/

archive/

bronze/

silver/

gold/

logs/

checkpoints/
```

---

# Databricks

## Função

Principal ambiente de processamento.

Será responsável por:

- Apache Spark
- Notebooks
- Jobs
- SQL
- Processamento distribuído

## Motivo da escolha

Databricks tornou-se uma das plataformas mais utilizadas em projetos modernos de Engenharia de Dados baseados em Lakehouse.

---

# Apache Spark

## Função

Motor de processamento distribuído.

Será utilizado para:

- Transformações
- Limpeza
- Enriquecimento
- Agregações
- Processamento em larga escala

## Conceitos estudados

- DataFrames
- Lazy Evaluation
- Particionamento
- Otimização
- Catalyst Optimizer

---

# Delta Lake

## Função

Formato oficial de armazenamento da plataforma.

Características:

- ACID
- Versionamento
- Time Travel
- Merge
- Upsert
- Schema Evolution

## Motivo da escolha

Delta Lake é amplamente utilizado em arquiteturas Lakehouse e possui integração nativa com Databricks.

---

# dbt Core

## Função

Responsável pela camada analítica.

Será utilizado para:

- Modelagem dimensional
- Testes
- Documentação
- Lineage
- Modelos incrementais
- Snapshots

## Motivo da escolha

dbt tornou-se referência em Analytics Engineering e separa claramente as responsabilidades entre Engenharia de Dados e modelagem analítica.

---

# Power BI

## Função

Ferramenta de Business Intelligence.

Será utilizada para:

- Dashboards
- KPIs
- Indicadores
- Storytelling

A conexão será realizada diretamente com a camada Gold.

---

# GitHub Actions (Futuro)

## Função

Automatizar processos de desenvolvimento.

Possíveis automações:

- Testes
- Deploy
- Validação
- Qualidade

---

# Databricks Jobs (Futuro)

## Função

Orquestrar os pipelines da plataforma.

Inicialmente será suficiente para automatizar as execuções sem a necessidade de uma ferramenta dedicada como Apache Airflow.

---

# Inteligência Artificial (Futuro)

## Objetivo

Criar um assistente capaz de consultar a plataforma utilizando linguagem natural.

Fluxo esperado:

```
Usuário

↓

Pergunta

↓

LLM

↓

SQL

↓

Camada Gold

↓

Resposta
```

Esta funcionalidade representa a etapa mais avançada da plataforma.

---

# Tecnologias Avaliadas

Durante o planejamento algumas tecnologias foram consideradas, mas não serão utilizadas inicialmente.

| Tecnologia | Motivo |
|------------|--------|
| Apache Airflow | Complexidade desnecessária no início |
| Kafka | Streaming não é prioridade |
| Kubernetes | Escopo futuro |
| Terraform | Infraestrutura ainda pequena |
| Snowflake | Alto custo para projeto pessoal |
| Azure Data Factory | Databricks Jobs atende inicialmente |
| Azure Data Lake | Projeto padronizado em AWS |

Essas tecnologias poderão ser incorporadas futuramente.

---

# Evolução da Stack

A stack tecnológica foi planejada para crescer junto com a plataforma.

Conforme novos desafios surgirem, poderão ser adicionados:

- Apache Airflow
- Docker
- Terraform
- Kubernetes
- Kafka
- Great Expectations
- Unity Catalog
- MLflow
- LangChain
- OpenAI API
- Feature Store

Todas as novas tecnologias deverão possuir um objetivo claro e agregar valor ao projeto.

---

# Filosofia da Stack

A escolha das tecnologias não foi baseada apenas em popularidade.

Cada ferramenta foi selecionada considerando:

- Aderência ao mercado.
- Integração com as demais tecnologias.
- Facilidade de aprendizado.
- Possibilidade de evolução.
- Baixo custo operacional.

O objetivo é construir uma plataforma moderna, profissional e sustentável, permitindo compreender não apenas como utilizar cada tecnologia, mas também qual problema ela resolve dentro da arquitetura.