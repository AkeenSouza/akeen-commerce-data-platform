# 07 - Architecture Decision Records (ADR)

# Objetivo

Este documento registra todas as decisões arquiteturais relevantes da **Akeen Commerce Data Platform (ACDP)**.

O objetivo é manter um histórico técnico da evolução da plataforma, documentando não apenas as decisões tomadas, mas também o contexto, as alternativas avaliadas e os impactos esperados.

Toda decisão que altere significativamente a arquitetura deverá possuir um ADR.

Este documento é considerado uma fonte oficial da arquitetura da plataforma.

---

# Como utilizar este documento

Sempre que uma decisão arquitetural importante for tomada:

1. Criar um novo ADR.
2. Nunca alterar um ADR antigo para refletir uma nova decisão.
3. Caso uma decisão seja substituída, criar um novo ADR referenciando o anterior.
4. Manter o histórico da evolução da arquitetura.

Cada ADR deverá possuir:

- Identificador
- Data
- Status
- Contexto
- Decisão
- Consequências
- Alternativas consideradas

---

# Status possíveis

| Status | Descrição |
|----------|----------------------------|
| Proposto | Ainda em discussão |
| Aceito | Aprovado para utilização |
| Substituído | Existe uma decisão mais recente |
| Descontinuado | Não será mais utilizado |

---

# Template

---

## ADR-XXX

### Título

---

### Status

Proposto

---

### Data

AAAA-MM-DD

---

### Contexto

Descreva o problema que motivou esta decisão.

---

### Decisão

Explique qual decisão foi tomada.

---

### Motivos

Explique por que esta decisão foi escolhida.

---

### Alternativas Avaliadas

Liste outras alternativas consideradas.

---

### Consequências

Explique os impactos positivos e negativos desta decisão.

---

# ADR-001

## Utilizar AWS como provedor de nuvem

### Status

Aceito

### Data

2026-07-01

### Contexto

Era necessário escolher um provedor de nuvem para hospedar o Data Lake e os demais componentes da plataforma.

### Decisão

A plataforma utilizará AWS como provedor principal.

### Motivos

- Familiaridade do desenvolvedor.
- Baixo custo para pequenos projetos.
- Grande adoção no mercado.
- Excelente integração com Databricks.
- Facilidade para expansão futura.

### Alternativas Avaliadas

- Azure
- Google Cloud

### Consequências

Positivas

- Curva de aprendizado menor.
- Integração simples com S3.

Negativas

- Parte da documentação ficará específica para AWS.

---

# ADR-002

## Utilizar Amazon S3 como Data Lake

### Status

Aceito

### Data

2026-07-01

### Contexto

Era necessário definir onde os dados seriam armazenados.

### Decisão

Utilizar Amazon S3.

### Motivos

- Baixo custo.
- Alta durabilidade.
- Escalabilidade praticamente ilimitada.
- Padrão do mercado.

### Alternativas Avaliadas

- Azure Data Lake
- Google Cloud Storage
- MinIO

### Consequências

A arquitetura permanece desacoplada do mecanismo de processamento.

---

# ADR-003

## Utilizar Arquitetura Lakehouse

### Status

Aceito

### Data

2026-07-01

### Contexto

Era necessário definir o padrão arquitetural da plataforma.

### Decisão

Adotar arquitetura Lakehouse.

### Motivos

- Flexibilidade.
- Baixo custo.
- Grande adoção pelo mercado.
- Compatibilidade com Databricks.

### Alternativas Avaliadas

- Data Warehouse tradicional
- Data Lake puro

### Consequências

A plataforma utilizará separação entre armazenamento e processamento.

---

# ADR-004

## Utilizar Arquitetura Medallion

### Status

Aceito

### Data

2026-07-01

### Contexto

Era necessário organizar os dados dentro do Data Lake.

### Decisão

Adotar Bronze, Silver e Gold.

### Motivos

- Organização.
- Separação de responsabilidades.
- Facilidade de manutenção.
- Padrão Databricks.

### Consequências

Todos os pipelines deverão respeitar esta divisão.

---

# ADR-005

## Utilizar Delta Lake

### Status

Aceito

### Data

2026-07-01

### Contexto

Era necessário definir o formato de armazenamento.

### Decisão

Utilizar Delta Lake.

### Motivos

- ACID.
- Merge.
- Time Travel.
- Schema Evolution.
- Integração nativa com Databricks.

### Alternativas Avaliadas

- Parquet
- Iceberg
- Hudi

### Consequências

Todas as tabelas persistidas utilizarão Delta.

---

# ADR-006

## Utilizar Apache Spark para processamento

### Status

Aceito

### Data

2026-07-01

### Contexto

Era necessário escolher a engine de processamento.

### Decisão

Apache Spark.

### Motivos

- Mercado.
- Escalabilidade.
- Integração com Databricks.

### Alternativas Avaliadas

- Pandas
- DuckDB
- Trino

### Consequências

Todas as transformações distribuídas utilizarão Spark.

---

# ADR-007

## Utilizar dbt apenas para modelagem analítica

### Status

Aceito

### Data

2026-07-01

### Contexto

Era necessário definir a responsabilidade do dbt.

### Decisão

O dbt será responsável apenas pela camada Gold.

### Motivos

- Separação de responsabilidades.
- Organização.
- Analytics Engineering.
- Melhor manutenção.

### Alternativas Avaliadas

- Fazer toda transformação no dbt.
- Fazer tudo no Spark.

### Consequências

Transformações técnicas ficam no Spark.

Regras analíticas ficam no dbt.

---

# ADR-008

## Utilizar Git Flow simplificado

### Status

Aceito

### Data

2026-07-01

### Decisão

A plataforma utilizará:

main

develop

feature/*

### Motivos

Fluxo simples.

Boa organização.

Facilidade para estudos.

---

# ADR-009

## Utilizar Claude Desktop como Assistente Técnico Oficial

### Status

Aceito

### Data

2026-07-01

### Contexto

O projeto utilizará Inteligência Artificial durante todo o desenvolvimento.

### Decisão

Claude Desktop será considerado uma ferramenta oficial da plataforma.

### Motivos

- Explicação de conceitos.
- Revisão arquitetural.
- Geração de documentação.
- Code Review.
- Apoio ao aprendizado.

### Consequências

Toda implementação deverá ser discutida antes da codificação.

---

# Evolução

Este documento deverá crescer continuamente.

Toda decisão arquitetural importante deverá possuir um ADR próprio.

Nenhuma decisão relevante deverá depender exclusivamente da memória do desenvolvedor ou das conversas com a IA.