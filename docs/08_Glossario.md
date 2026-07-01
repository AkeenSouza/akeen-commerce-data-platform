# 08 - Glossário

# Objetivo

Este documento reúne os principais termos utilizados ao longo da construção da **Akeen Commerce Data Platform (ACDP)**.

O objetivo é servir como referência rápida durante o desenvolvimento da plataforma, facilitando o entendimento dos conceitos de Engenharia de Dados, Analytics Engineering, Computação em Nuvem, Business Intelligence e Inteligência Artificial.

Este documento deverá evoluir continuamente conforme novas tecnologias forem incorporadas ao projeto.

---

# Como utilizar

Sempre que um novo conceito importante surgir durante o projeto, ele deverá ser registrado neste glossário.

Cada termo deve conter:

- Nome
- Definição
- Contexto de uso na plataforma

---

# Engenharia de Dados

## Data Lake

Repositório centralizado para armazenamento de dados estruturados, semiestruturados e não estruturados.

Na ACDP será implementado utilizando Amazon S3.

---

## Lakehouse

Arquitetura que combina características de Data Lakes e Data Warehouses.

Permite armazenar grandes volumes de dados mantendo recursos como ACID, versionamento e processamento analítico.

---

## Medallion Architecture

Arquitetura baseada em três camadas:

- Bronze
- Silver
- Gold

Cada camada possui responsabilidades específicas.

---

## ETL

Extract, Transform and Load.

Processo onde os dados são transformados antes de serem carregados no destino.

---

## ELT

Extract, Load and Transform.

Processo onde os dados são carregados primeiro e transformados posteriormente.

É o padrão utilizado neste projeto.

---

## Pipeline

Conjunto de etapas responsáveis pelo processamento dos dados.

Exemplo:

Extração → Bronze → Silver → Gold

---

## Batch Processing

Processamento realizado em intervalos programados.

Inicialmente toda a plataforma funcionará em modo Batch.

---

## Streaming

Processamento contínuo de eventos em tempo real.

Poderá ser incorporado futuramente.

---

# Arquitetura

## Arquitetura em Camadas

Estratégia que divide a plataforma em componentes independentes.

Na ACDP serão utilizadas:

- Ingestion Layer
- Storage Layer
- Processing Layer
- Serving Layer
- Consumption Layer

---

## Baixo Acoplamento

Princípio onde componentes possuem pouca dependência entre si.

Facilita manutenção e evolução da plataforma.

---

## Alta Coesão

Princípio onde cada componente possui responsabilidades bem definidas.

---

## Escalabilidade

Capacidade da plataforma crescer mantendo desempenho.

---

## Reprodutibilidade

Capacidade de executar novamente um pipeline obtendo resultados consistentes.

---

## Idempotência

Característica de uma operação que produz o mesmo resultado mesmo sendo executada várias vezes.

---

## ADR

Architecture Decision Record.

Documento utilizado para registrar decisões arquiteturais importantes.

---

# Apache Spark

## Spark

Engine de processamento distribuído utilizada para grandes volumes de dados.

---

## PySpark

API do Apache Spark para Python.

Será utilizada na maioria das transformações.

---

## Spark SQL

Interface SQL do Spark.

Permite consultar DataFrames utilizando SQL.

---

## DataFrame

Estrutura tabular distribuída utilizada pelo Spark.

Equivale a uma tabela em memória.

---

## Lazy Evaluation

O Spark somente executa uma operação quando uma Action é chamada.

Esse comportamento permite otimizações automáticas.

---

## Partition

Divisão física dos dados utilizada para processamento distribuído.

---

# Delta Lake

## Delta Table

Tabela armazenada utilizando o formato Delta Lake.

---

## ACID

Conjunto de propriedades que garantem consistência das transações.

---

## Time Travel

Funcionalidade que permite consultar versões anteriores de uma tabela.

---

## Merge

Operação utilizada para realizar Upserts.

---

## Upsert

Atualiza registros existentes e insere novos registros em uma única operação.

---

## Vacuum

Processo responsável pela remoção de arquivos antigos do Delta Lake.

---

## Optimize

Operação utilizada para reorganizar arquivos e melhorar performance.

---

# dbt

## dbt

Ferramenta de Analytics Engineering responsável pela camada analítica.

---

## Model

Consulta SQL responsável por gerar uma tabela ou view.

---

## Seed

Arquivo estático utilizado como origem de dados.

---

## Snapshot

Permite acompanhar alterações históricas em registros.

---

## Incremental Model

Modelo que processa apenas novos registros.

---

## Test

Validação automática aplicada sobre os dados.

---

## Lineage

Representação gráfica da dependência entre modelos.

---

# Git

## Repository

Local onde todo o código do projeto é armazenado.

---

## Commit

Registro de uma alteração realizada no projeto.

---

## Branch

Linha independente de desenvolvimento.

---

## Merge

União entre duas branches.

---

## Pull Request

Solicitação para incorporar alterações em outra branch.

---

## Main

Branch principal do projeto.

---

## Develop

Branch utilizada para integração das funcionalidades.

---

# AWS

## AWS

Amazon Web Services.

Provedor de nuvem utilizado pelo projeto.

---

## Amazon S3

Serviço utilizado como Data Lake.

---

## IAM

Serviço responsável pelo gerenciamento de permissões.

Poderá ser utilizado futuramente.

---

# Business Intelligence

## Dashboard

Painel utilizado para visualização de indicadores.

---

## KPI

Key Performance Indicator.

Indicador utilizado para medir desempenho do negócio.

---

## Star Schema

Modelo dimensional composto por tabelas fato e dimensões.

---

## Fact Table

Tabela que armazena métricas do negócio.

---

## Dimension Table

Tabela que descreve entidades do negócio.

---

# Inteligência Artificial

## LLM

Large Language Model.

Modelo de linguagem utilizado para compreender linguagem natural.

---

## Prompt

Instrução enviada para um modelo de IA.

---

## Prompt Engineering

Conjunto de técnicas utilizadas para construir prompts eficientes.

---

## AI Agent

Sistema que utiliza um LLM para executar tarefas de forma autônoma.

---

## MCP

Model Context Protocol.

Protocolo utilizado para permitir que modelos de IA interajam com ferramentas externas, como arquivos, bancos de dados e APIs.

---

# Engenharia de Software

## Refactoring

Reorganização do código sem alterar seu comportamento.

---

## Code Review

Revisão técnica do código antes da integração.

---

## Logging

Registro das execuções da aplicação.

---

## CI/CD

Integração Contínua e Entrega Contínua.

Processo automatizado de validação e implantação.

---

## Observabilidade

Capacidade de compreender o comportamento da plataforma através de métricas, logs e monitoramento.

---

## Data Quality

Conjunto de práticas destinadas a garantir a qualidade dos dados.

---

## DataOps

Aplicação dos princípios de DevOps ao ciclo de vida dos dados.

---

# Próximos Conceitos

Este glossário deverá crescer conforme novas tecnologias forem incorporadas.

Alguns conceitos previstos para futuras versões:

- Docker
- Terraform
- Kubernetes
- Apache Airflow
- Apache Kafka
- Unity Catalog
- Great Expectations
- MLflow
- Feature Store
- Data Contracts
- Data Mesh
- Data Catalog
- MLOps
- RAG (Retrieval-Augmented Generation)
- Embeddings
- Vector Database