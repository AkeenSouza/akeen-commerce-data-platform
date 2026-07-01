# 02 - Arquitetura da Plataforma

# Arquitetura Geral
--teste
## Objetivo

Este documento descreve a arquitetura da **Akeen Commerce Data Platform (ACDP)**.

A plataforma foi projetada seguindo o paradigma **Lakehouse**, utilizando uma arquitetura em camadas (Medallion Architecture) para separar responsabilidades, facilitar a manutenção, garantir escalabilidade e permitir a evolução contínua da solução.

Embora seja um projeto pessoal, todas as decisões arquiteturais buscam refletir práticas utilizadas por empresas modernas de Engenharia de Dados.

---

# Princípios Arquiteturais

A arquitetura da plataforma segue os seguintes princípios:

- Separação clara de responsabilidades.
- Dados imutáveis sempre que possível.
- Reprodutibilidade dos pipelines.
- Escalabilidade horizontal.
- Processamento distribuído.
- Baixo acoplamento entre componentes.
- Alta observabilidade.
- Facilidade de manutenção.
- Evolução incremental.

---

# Visão Geral da Arquitetura

```
                  Fontes de Dados
        ┌──────────────────────────────────┐
        │ APIs │ CSV │ JSON │ Kaggle │ ERP │
        └──────────────────────────────────┘
                       │
                       ▼
             Camada de Ingestão
                 (Python)
                       │
                       ▼
              AWS S3 Data Lake
                       │
         ┌─────────────┴─────────────┐
         ▼                           ▼
      Raw Zone                  Archive
                       │
                       ▼
          Bronze (Delta Lake)
                       │
                       ▼
        Apache Spark / Databricks
                       │
                Transformações
                       │
                       ▼
          Silver (Delta Lake)
                       │
                    dbt Core
                       │
                       ▼
           Gold (Star Schema)
              │            │
              ▼            ▼
         Power BI      IA / LLM
```

---

# Componentes da Plataforma

## Fontes de Dados

A plataforma deverá consumir dados provenientes de diferentes tipos de sistemas, simulando um ambiente corporativo.

Exemplos:

- APIs REST
- Arquivos CSV
- Arquivos JSON
- Arquivos Excel
- Arquivos Parquet
- Datasets públicos
- Dados simulados de sistemas ERP

O objetivo é representar diferentes cenários encontrados em projetos reais.

---

## Camada de Ingestão

Responsável por coletar os dados das fontes externas.

Principais responsabilidades:

- Download dos dados.
- Controle de execução.
- Padronização mínima.
- Registro de logs.
- Persistência inicial no Data Lake.

Nesta etapa não deverão existir regras de negócio.

---

## Data Lake

O Data Lake será implementado utilizando **Amazon S3**.

Ele será responsável apenas pelo armazenamento dos dados.

Estrutura inicial:

```
data-lake/

raw/

archive/

bronze/

silver/

gold/

logs/

checkpoints/
```

Cada diretório possui responsabilidades específicas e independentes.

---

# Arquitetura Medallion

A plataforma utilizará a arquitetura Medallion composta por três camadas principais.

## Bronze

Objetivo:

Persistir os dados exatamente como foram recebidos.

Características:

- Dados brutos.
- Histórico completo.
- Sem regras de negócio.
- Conversão para Delta Lake.
- Auditoria.
- Controle de ingestão.

A camada Bronze funciona como a "fonte de verdade" dentro do Data Lake.

---

## Silver

Objetivo:

Construir dados confiáveis.

Nesta camada ocorrerão transformações como:

- Tratamento de tipos.
- Limpeza de dados.
- Remoção de duplicidades.
- Normalização.
- Padronização.
- Enriquecimento.
- Correção de inconsistências.

Os dados Silver devem estar preparados para reutilização por diferentes consumidores.

---

## Gold

Objetivo:

Disponibilizar dados para consumo analítico.

Nesta camada serão construídos:

- Dimensões
- Tabelas fato
- KPIs
- Indicadores
- Métricas de negócio

A modelagem seguirá, preferencialmente, o modelo dimensional (Star Schema).

---

# Processamento

Todo o processamento será realizado utilizando **Apache Spark** executando no **Databricks**.

As transformações serão divididas em etapas independentes.

Fluxo esperado:

```
Bronze

↓

Limpeza

↓

Padronização

↓

Silver

↓

Modelagem

↓

Gold
```

Sempre que possível os pipelines deverão ser modulares e reutilizáveis.

---

# Analytics Engineering

A camada Gold será construída utilizando **dbt Core**.

Responsabilidades do dbt:

- Modelagem SQL.
- Organização dos modelos.
- Testes automatizados.
- Documentação.
- Data Lineage.
- Modelos incrementais.
- Snapshots.

Toda lógica de negócio deverá ser centralizada nesta camada sempre que fizer sentido.

---

# Consumo dos Dados

Inicialmente existirão dois consumidores principais.

## Business Intelligence

Power BI

Responsável pela construção de dashboards executivos.

Exemplos:

- Receita
- Clientes
- Produtos
- Pedidos
- Estoque
- Marketing

---

## Inteligência Artificial

Em uma fase posterior será implementado um agente baseado em LLM.

Este agente deverá ser capaz de:

- Interpretar perguntas em linguagem natural.
- Gerar consultas SQL.
- Consultar a camada Gold.
- Explicar os resultados ao usuário.

---

# Fluxo Geral da Plataforma

```
Fonte

↓

Ingestão

↓

Data Lake

↓

Bronze

↓

Spark

↓

Silver

↓

dbt

↓

Gold

↓

Power BI

↓

IA
```

---

# Organização dos Pipelines

Cada pipeline deverá possuir responsabilidades bem definidas.

Exemplo:

```
Clientes

Extração

↓

Bronze

↓

Silver

↓

Gold

↓

Dashboard
```

A mesma estrutura será utilizada para todos os domínios da empresa.

---

# Observabilidade

Toda execução deverá gerar informações suficientes para acompanhamento da plataforma.

Sempre que possível deverão existir:

- Logs
- Tempo de execução
- Quantidade de registros
- Erros
- Alertas
- Histórico de execuções

Essas informações permitirão acompanhar a saúde da plataforma.

---

# Escalabilidade

A arquitetura foi planejada para permitir crescimento gradual.

Novos componentes poderão ser incorporados sem necessidade de reestruturar a plataforma.

Exemplos:

- Apache Airflow
- Kafka
- Terraform
- Docker
- Kubernetes
- Unity Catalog
- Great Expectations
- Machine Learning
- MLOps
- Data Contracts

---

# Decisões Arquiteturais

As principais decisões de arquitetura serão documentadas separadamente utilizando **Architecture Decision Records (ADR)**.

Cada ADR deverá responder:

- Qual decisão foi tomada?
- Por que ela foi escolhida?
- Quais alternativas foram avaliadas?
- Quais impactos essa decisão possui?

Essa abordagem permitirá manter o histórico técnico da evolução da plataforma.

---

# Considerações Finais

A arquitetura da Akeen Commerce Data Platform foi projetada para equilibrar simplicidade, aprendizado e aderência às práticas modernas de Engenharia de Dados.

Embora o projeto tenha finalidade educacional, sua estrutura busca refletir uma plataforma corporativa real, permitindo que novos componentes sejam adicionados de forma organizada, mantendo baixo acoplamento, alta reutilização e facilidade de manutenção.