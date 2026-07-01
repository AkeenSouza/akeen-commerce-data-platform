# Akeen Commerce Data Platform

> Plataforma moderna de Engenharia de Dados construída para simular um ambiente corporativo real utilizando arquitetura Lakehouse.

---

# 📖 Sobre o Projeto

O **Akeen Commerce Data Platform (ACDP)** é um projeto pessoal criado com o objetivo de desenvolver experiência prática nas principais tecnologias utilizadas por Engenheiros de Dados modernos.

A proposta não é apenas construir pipelines de dados, mas sim simular uma plataforma corporativa completa, desde a ingestão dos dados até sua disponibilização para Analytics, Business Intelligence e Inteligência Artificial.

Todo o projeto seguirá boas práticas de arquitetura, versionamento, documentação, governança e qualidade de dados, aproximando-se do ambiente encontrado em empresas de médio e grande porte.

---

# 🎯 Objetivos

Este projeto busca desenvolver experiência prática em:

- Arquitetura Lakehouse
- Engenharia de Dados
- Analytics Engineering
- DataOps
- Business Intelligence
- Data Quality
- Data Lineage
- Versionamento com Git
- Boas práticas de arquitetura
- Integração com Inteligência Artificial

---

# 🏢 Empresa Fictícia

O projeto simula a empresa fictícia **Akeen Commerce**, um e-commerce que possui diversas áreas de negócio.

Domínios de dados:

- Clientes
- Produtos
- Pedidos
- Pagamentos
- Estoque
- Entregas
- Marketing

Todos os dados serão tratados como se fossem provenientes de sistemas corporativos reais.

---

# 🏛 Arquitetura

```
                  APIs
             CSV • JSON • Kaggle
                     │
                     ▼
             Camada de Ingestão
                  (Python)
                     │
                     ▼
            Data Lake (AWS S3)
                     │
              Bronze (Delta)
                     │
                     ▼
         Databricks + Apache Spark
                     │
              Transformações
                     │
                     ▼
              Silver (Delta)
                     │
                 dbt Core
                     │
                     ▼
         Gold (Modelo Dimensional)
              │                │
              ▼                ▼
         Power BI         IA / LLM
```

---

# 🛠 Stack Tecnológica

| Categoria | Tecnologia |
|------------|------------|
| Cloud | AWS |
| Data Lake | Amazon S3 |
| Processamento | Databricks |
| Engine | Apache Spark |
| Linguagem | Python |
| SQL | Spark SQL |
| Analytics Engineering | dbt Core |
| Storage | Delta Lake |
| Versionamento | Git + GitHub |
| BI | Power BI |
| IDE | Visual Studio Code |
| IA | LLM (futuro) |

---

# 📂 Estrutura do Projeto

```
Akeen-Commerce/

│
├── README.md
├── 01_Visao_Geral.md
├── 02_Arquitetura.md
├── 03_Roadmap.md
├── 04_Stack.md
├── 05_Padroes.md
├── 06_Convencoes.md
├── 07_Decisoes.md
├── 08_Backlog.md
├── 09_Glossario.md
│
├── ingestion/
├── spark/
├── notebooks/
├── dbt/
├── datasets/
├── dashboards/
├── infrastructure/
├── tests/
└── docs/
```

---

# 🏗 Arquitetura de Dados

O projeto utiliza a arquitetura **Medallion (Bronze, Silver e Gold)**.

## Bronze

Dados ingeridos exatamente como chegam das fontes.

Responsabilidades:

- Persistência
- Auditoria
- Histórico
- Conversão para Delta

---

## Silver

Camada responsável pela padronização dos dados.

Responsabilidades:

- Limpeza
- Tratamento de tipos
- Remoção de duplicidades
- Normalização
- Enriquecimento

---

## Gold

Camada destinada ao consumo analítico.

Responsabilidades:

- Modelo dimensional
- KPIs
- Dashboards
- Analytics
- IA

---

# 🚀 Roadmap

## Fase 1
Infraestrutura

- Git
- GitHub
- AWS
- S3
- Databricks

---

## Fase 2

Ingestão de Dados

- APIs
- CSV
- JSON
- Delta Bronze

---

## Fase 3

Transformações

- Apache Spark
- PySpark
- Spark SQL
- Silver

---

## Fase 4

Analytics Engineering

- dbt
- Testes
- Documentação
- Lineage
- Gold

---

## Fase 5

Business Intelligence

- Power BI
- Dashboards
- KPIs

---

## Fase 6

DataOps

- Testes
- Monitoramento
- Logs
- CI/CD

---

## Fase 7

Inteligência Artificial

- Agente SQL
- Chat com dados
- Insights automáticos

---

# 📚 Documentação

Toda a documentação do projeto está organizada em arquivos Markdown.

Cada documento possui um objetivo específico para facilitar a manutenção e evolução da plataforma.

---

# 📈 Evolução

Este projeto será desenvolvido de forma incremental.

Novas tecnologias poderão ser incorporadas ao longo do tempo, como:

- Apache Airflow
- Terraform
- Docker
- Kubernetes
- Kafka
- Unity Catalog
- Data Contracts
- Great Expectations
- Machine Learning
- MLOps

---

# 💡 Filosofia do Projeto

Mais importante do que "fazer funcionar" é compreender profundamente os conceitos de Engenharia de Dados.

Cada decisão arquitetural deverá ser documentada, justificada e implementada utilizando boas práticas de mercado.

O objetivo é construir um portfólio profissional que demonstre conhecimentos técnicos, capacidade de arquitetura e organização de projetos reais.

---

# 👨‍💻 Autor

Projeto desenvolvido por **Akeen Souza Moreira** como parte de sua jornada de especialização em Engenharia de Dados, Analytics Engineering e Arquitetura de Dados Moderna.