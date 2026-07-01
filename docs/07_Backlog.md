# 07 - Backlog

# Product Backlog

## Objetivo

Este documento registra todas as funcionalidades planejadas para a evolução da **Akeen Commerce Data Platform (ACDP)**.

O backlog funciona como a principal fonte de planejamento do projeto.

Novas ideias, melhorias e funcionalidades deverão ser registradas aqui antes de serem implementadas.

Este documento é vivo e será atualizado continuamente durante o desenvolvimento.

---

# Legenda

| Prioridade | Significado |
|------------|------------|
| 🔴 Alta | Essencial para evolução da plataforma |
| 🟡 Média | Importante, mas pode aguardar |
| 🟢 Baixa | Melhoria futura |
| 🔵 Ideia | Ainda em avaliação |

---

| Status | Significado |
|---------|------------|
| ⏳ Planejado | Ainda não iniciado |
| 🚧 Em Desenvolvimento | Em andamento |
| ✅ Concluído | Finalizado |
| ❌ Cancelado | Não será implementado |

---

# Épico 1 — Fundação da Plataforma

## Objetivo

Criar toda a estrutura inicial da plataforma.

---

### BK-001

**Título**

Criar estrutura do repositório

Prioridade

🔴 Alta

Status

⏳ Planejado

Critérios de aceite

- Estrutura criada
- Pastas organizadas
- README criado

---

### BK-002

Criar documentação inicial

🔴 Alta

⏳ Planejado

---

### BK-003

Configurar Git

🔴 Alta

⏳ Planejado

---

### BK-004

Configurar GitHub

🔴 Alta

⏳ Planejado

---

### BK-005

Configurar VS Code

🟡 Média

⏳ Planejado

---

# Épico 2 — Ingestão

## Objetivo

Construir pipelines de ingestão.

---

### BK-006

Criar pipeline para APIs

🔴 Alta

⏳ Planejado

---

### BK-007

Criar pipeline para CSV

🔴 Alta

⏳ Planejado

---

### BK-008

Criar pipeline para JSON

🟡 Média

⏳ Planejado

---

### BK-009

Criar controle de logs

🟡 Média

⏳ Planejado

---

### BK-010

Criar controle de execução

🟡 Média

⏳ Planejado

---

# Épico 3 — Data Lake

---

### BK-011

Criar estrutura Bronze

🔴 Alta

⏳ Planejado

---

### BK-012

Criar estrutura Silver

🔴 Alta

⏳ Planejado

---

### BK-013

Criar estrutura Gold

🔴 Alta

⏳ Planejado

---

### BK-014

Implementar Delta Lake

🔴 Alta

⏳ Planejado

---

### BK-015

Implementar Time Travel

🟡 Média

⏳ Planejado

---

# Épico 4 — Apache Spark

---

### BK-016

Criar pipeline Bronze → Silver

🔴 Alta

⏳ Planejado

---

### BK-017

Criar pipeline Silver → Gold

🔴 Alta

⏳ Planejado

---

### BK-018

Padronizar transformações

🟡 Média

⏳ Planejado

---

### BK-019

Implementar tratamento de erros

🟡 Média

⏳ Planejado

---

### BK-020

Criar biblioteca compartilhada

🟢 Baixa

⏳ Planejado

---

# Épico 5 — dbt

---

### BK-021

Criar projeto dbt

🔴 Alta

⏳ Planejado

---

### BK-022

Criar primeira dimensão

🔴 Alta

⏳ Planejado

---

### BK-023

Criar primeira tabela fato

🔴 Alta

⏳ Planejado

---

### BK-024

Implementar testes

🟡 Média

⏳ Planejado

---

### BK-025

Gerar documentação

🟡 Média

⏳ Planejado

---

# Épico 6 — Business Intelligence

---

### BK-026

Criar dashboard executivo

🔴 Alta

⏳ Planejado

---

### BK-027

Criar dashboard comercial

🟡 Média

⏳ Planejado

---

### BK-028

Criar dashboard financeiro

🟡 Média

⏳ Planejado

---

# Épico 7 — Qualidade

---

### BK-029

Criar testes de Data Quality

🔴 Alta

⏳ Planejado

---

### BK-030

Criar monitoramento

🟡 Média

⏳ Planejado

---

### BK-031

Criar auditoria

🟢 Baixa

⏳ Planejado

---

# Épico 8 — CI/CD

---

### BK-032

Criar GitHub Actions

🟡 Média

⏳ Planejado

---

### BK-033

Executar testes automaticamente

🟡 Média

⏳ Planejado

---

### BK-034

Automatizar deploy

🟢 Baixa

⏳ Planejado

---

# Épico 9 — Inteligência Artificial

---

### BK-035

Criar agente SQL

🔴 Alta

⏳ Planejado

---

### BK-036

Responder perguntas em linguagem natural

🔴 Alta

⏳ Planejado

---

### BK-037

Gerar insights automaticamente

🟡 Média

⏳ Planejado

---

### BK-038

Explicar KPIs

🟢 Baixa

⏳ Planejado

---

# Melhorias Futuras

## Plataforma

- Docker
- Terraform
- Kubernetes
- Kafka
- Airflow
- Unity Catalog
- MLflow

---

## Engenharia

- Testes unitários
- Testes de integração
- Observabilidade
- Métricas
- Data Contracts
- Feature Store

---

## IA

- Chat interno
- Agentes especializados
- Documentação automática
- Geração automática de pipelines
- Revisão automática de código
- Sugestões arquiteturais

---

# Ideias

Esta seção registra ideias que ainda não foram priorizadas.

- Criar catálogo de dados
- Criar portal interno da plataforma
- Criar API para consulta dos dados
- Criar ambiente multiusuário
- Criar monitor em tempo real
- Criar simulador de cargas
- Criar ambiente de homologação
- Criar dashboards de monitoramento da própria plataforma

---

# Definition of Done (DoD)

Uma funcionalidade será considerada concluída quando:

- Código implementado.
- Documentação atualizada.
- Commit realizado.
- Testes executados.
- ADR criado (quando necessário).
- Revisão técnica concluída.
- Arquitetura validada.
- Sem pendências conhecidas.

---

# Observações

O backlog representa a visão atual da evolução da plataforma.

Novas funcionalidades poderão ser adicionadas, removidas ou repriorizadas conforme o projeto evoluir.

O objetivo é manter um planejamento claro, permitindo que a plataforma cresça de forma organizada e sustentável.