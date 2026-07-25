# ☕ Akeen Coffee Commerce Data Platform (ACDP)

> Plataforma moderna de Engenharia de Dados desenvolvida para simular um ambiente corporativo real de um e-commerce especializado em cafés especiais, utilizando arquitetura Lakehouse, DataOps e Analytics Engineering.

---

# 📖 Sobre o Projeto

O **Akeen Coffee Commerce Data Platform (ACDP)** é um projeto pessoal criado para consolidar conhecimentos em Engenharia de Dados Moderna através da construção de uma plataforma end-to-end.

Mais do que desenvolver pipelines, o objetivo é reproduzir desafios encontrados em empresas reais, aplicando boas práticas de arquitetura, governança, qualidade de dados, observabilidade, versionamento e documentação.

Todo o projeto será desenvolvido de forma incremental, priorizando aprendizado profundo sobre cada tecnologia utilizada.

---

# 🎯 Objetivos

Este projeto tem como objetivo desenvolver experiência prática em:

* Arquitetura Lakehouse
* Engenharia de Dados
* Analytics Engineering
* DataOps
* Data Quality
* Data Modeling
* Data Lineage
* Apache Spark
* Delta Lake
* dbt
* Cloud Computing (AWS)
* Business Intelligence
* Inteligência Artificial aplicada a dados

---

# ☕ Empresa Fictícia

A **Akeen Coffee Commerce** é uma empresa fictícia especializada na venda de cafés especiais, grãos, acessórios e produtos relacionados ao universo do café.

O domínio foi escolhido por representar um tema de interesse pessoal, permitindo construir uma plataforma tecnicamente sólida sobre um negócio compreendido em profundidade.

A arquitetura foi projetada para permitir a expansão gradual de novos domínios de negócio, simulando a evolução natural de uma empresa real.

Domínios contemplados pelo projeto:

* Clientes
* Produtos
* Pedidos
* Pagamentos
* Estoque
* Entregas
* Marketing

---

# 🏛 Arquitetura

```text
                 Fontes de Dados
              CSV • JSON • Kaggle
                     │
                     ▼
            Camada de Ingestão
                  (Python)
                     │
                     ▼
             AWS S3 Data Lake
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
          Gold (Star Schema)
              │            │
              ▼            ▼
         Power BI      IA / LLM
```

---

# 🛠 Stack Tecnológica

| Categoria             | Tecnologia   |
| --------------------- | ------------ |
| Cloud                 | AWS          |
| Data Lake             | Amazon S3    |
| Processamento         | Databricks   |
| Engine                | Apache Spark |
| Linguagem             | Python       |
| SQL                   | Spark SQL    |
| Analytics Engineering | dbt Core     |
| Storage               | Delta Lake   |
| Versionamento         | Git + GitHub |
| BI                    | Power BI     |
| IA                    | LLMs         |

---

# 📂 Estrutura do Projeto

```text
Akeen-Coffee-Commerce/

├── README.md
├── MEMORY.md
├── PROJECT_CONTEXT.md
├── CHANGELOG.md
│
├── docs/
│   ├── ADR/
│   ├── architecture/
│   ├── diagrams/
│   └── decisions/
│
├── datasets/
├── src/
├── spark/
├── dbt/
├── dashboards/
├── infrastructure/
└── tests/
```

---

# 🏗 Arquitetura de Dados

O projeto segue a arquitetura **Medallion (Bronze, Silver e Gold)**.

### Bronze

Persistência dos dados exatamente como recebidos da origem.

### Silver

Padronização, limpeza, tipagem, deduplicação e enriquecimento.

### Gold

Modelagem dimensional para consumo analítico, dashboards e aplicações de IA.

---

# 🚀 Roadmap

* **Fase 1** — Infraestrutura
* **Fase 2** — Ingestão de Dados
* **Fase 3** — Transformações com Spark
* **Fase 4** — Analytics Engineering com dbt
* **Fase 5** — Business Intelligence
* **Fase 6** — DataOps
* **Fase 7** — Inteligência Artificial

---

# 📚 Documentação

A documentação do projeto é organizada em arquivos independentes.

| Documento            | Objetivo                                                            |
| -------------------- | ------------------------------------------------------------------- |
| `README.md`          | Visão geral do projeto                                              |
| `MEMORY.md`          | Memória viva do projeto e decisões permanentes                      |
| `PROJECT_CONTEXT.md` | Contexto permanente utilizado pelo projeto                          |
| `CHANGELOG.md`       | Histórico de evolução                                               |
| `docs/ADR/`          | Registros de Decisões Arquiteturais (Architecture Decision Records) |

---

# 💡 Filosofia

Mais importante do que construir uma plataforma funcionando é compreender profundamente os conceitos por trás de cada decisão arquitetural.

Todo componente implementado deve possuir uma justificativa técnica, documentação adequada e seguir boas práticas utilizadas por equipes modernas de Engenharia de Dados.

---

# 👨‍💻 Autor

**Akeen Souza Moreira**

Projeto desenvolvido como parte da jornada de especialização em Engenharia de Dados, Analytics Engineering e Arquitetura de Dados Moderna.
