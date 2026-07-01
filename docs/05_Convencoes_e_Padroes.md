# 05 - Padrões de Desenvolvimento

# Objetivo

Este documento define os padrões de desenvolvimento da **Akeen Commerce Data Platform (ACDP)**.

Seu objetivo é garantir consistência entre todos os componentes da plataforma, facilitando manutenção, evolução, legibilidade e colaboração.

Todas as implementações deverão seguir estas convenções, salvo quando houver uma justificativa técnica documentada.

---

# Princípios Gerais

Todo desenvolvimento deve priorizar:

- Simplicidade
- Clareza
- Reutilização
- Escalabilidade
- Baixo acoplamento
- Alta coesão
- Código legível
- Documentação
- Reprodutibilidade

Mais importante do que escrever código rapidamente é construir uma plataforma sustentável.

---

# Organização do Projeto

Cada componente deverá possuir uma responsabilidade única.

Exemplo:

```
ingestion/

spark/

dbt/

dashboards/

tests/

docs/

datasets/
```

Misturar responsabilidades dentro do mesmo diretório deve ser evitado.

---

# Organização das Camadas

A plataforma seguirá obrigatoriamente a arquitetura Medallion.

## Bronze

Responsável apenas pela persistência dos dados.

Permitido:

- Conversão para Delta
- Inclusão de metadados
- Controle de ingestão

Não permitido:

- Regras de negócio
- Agregações
- Correções complexas

---

## Silver

Responsável pela padronização dos dados.

Permitido:

- Limpeza
- Deduplicação
- Conversões
- Enriquecimento
- Padronização

---

## Gold

Responsável apenas pelo consumo analítico.

Permitido:

- Modelagem dimensional
- KPIs
- Métricas
- Agregações
- Dashboards

---

# Padrão de Nomenclatura

## Diretórios

Sempre utilizar:

snake_case

Exemplo:

```
data_lake/

spark_jobs/

raw_data/

customer_orders/
```

Nunca utilizar:

```
DataLake/

SparkJobs/

Nova Pasta/

MinhaTabela/
```

---

## Arquivos

Sempre utilizar:

```
load_customers.py

transform_orders.py

sales_dashboard.pbix

customer_dimension.sql
```

---

## Variáveis Python

Sempre utilizar:

snake_case

Exemplo:

```python
customer_id

order_date

total_sales
```

---

## Classes

Sempre utilizar:

PascalCase

Exemplo:

```python
CustomerLoader

SalesPipeline

ProductService
```

---

## Funções

Sempre utilizar:

snake_case

Exemplo:

```python
load_customers()

save_delta()

calculate_metrics()
```

---

## Constantes

Sempre utilizar:

UPPER_CASE

Exemplo:

```python
RAW_PATH

SILVER_PATH

DEFAULT_TIMEOUT
```

---

# SQL

Todo SQL deverá ser escrito priorizando legibilidade.

Exemplo:

```sql
SELECT

    customer_id,
    customer_name,
    order_total

FROM silver.orders

WHERE order_date >= CURRENT_DATE
```

Evitar:

```sql
SELECT * FROM ...
```

Sempre selecionar apenas as colunas necessárias.

---

# Organização dos Notebooks

Cada notebook deverá executar apenas uma responsabilidade.

Exemplo:

```
01_ingestion_customers

02_bronze_customers

03_silver_customers

04_gold_customers
```

Evitar notebooks extremamente longos contendo toda a pipeline.

---

# Modularização

Sempre que possível:

- separar funções
- reutilizar código
- evitar duplicação

Código repetido deve ser transformado em função ou módulo reutilizável.

---

# Logging

Todo pipeline deverá possuir logs.

Exemplos:

- início da execução
- término
- quantidade de registros
- tempo de execução
- erros

O objetivo é facilitar futuras investigações.

---

# Tratamento de Erros

Todo processo crítico deverá possuir tratamento de exceções.

Sempre que possível:

- registrar erro
- registrar contexto
- permitir investigação posterior

Evitar blocos:

```python
except:
    pass
```

---

# Versionamento

Todo desenvolvimento ocorrerá em branches.

Fluxo:

```
main

↓

develop

↓

feature/*
```

Exemplo:

```
feature/customer_ingestion

feature/dbt_sales

feature/dashboard_orders
```

---

# Commits

Os commits devem possuir mensagens claras.

Exemplos:

```
feat: add customer ingestion pipeline

fix: correct null handling in orders

docs: update architecture documentation

refactor: simplify bronze pipeline

test: add dbt tests for customers
```

Evitar:

```
teste

ajustes

novo

123

alteração
```

---

# Documentação

Toda funcionalidade relevante deverá possuir documentação.

Sempre documentar:

- objetivo
- entradas
- saídas
- dependências
- limitações

---

# Data Quality

Toda transformação importante deverá considerar:

- registros nulos
- duplicidades
- tipos incorretos
- datas inválidas
- valores negativos
- chaves inexistentes

Sempre que possível utilizar testes automatizados.

---

# Performance

Evitar processamento desnecessário.

Sempre considerar:

- leitura mínima
- filtros antecipados
- particionamento
- reutilização de DataFrames
- joins eficientes

O objetivo não é otimizar prematuramente, mas evitar más práticas.

---

# ADR (Architecture Decision Records)

Toda decisão importante deverá ser registrada.

Exemplos:

- escolha do S3
- escolha do Delta
- escolha do dbt
- mudança na arquitetura

Cada ADR deverá responder:

- Qual decisão?
- Por quê?
- Alternativas?
- Impactos?

---

# Filosofia de Código

Antes de escrever qualquer código, responder às seguintes perguntas:

- Este código é realmente necessário?
- Existe uma solução mais simples?
- Outra pessoa entenderia isso daqui a seis meses?
- Posso reutilizar esse componente?
- Esta implementação está coerente com a arquitetura?

Se alguma resposta for negativa, a implementação deve ser reavaliada.

---

# Papel da IA no Desenvolvimento

A IA será utilizada como uma ferramenta de apoio ao desenvolvimento.

Ela deverá auxiliar em:

- explicação de conceitos
- revisão de arquitetura
- geração de código
- revisão de código
- identificação de melhorias
- documentação
- brainstorming técnico

Entretanto, nenhuma implementação deverá ser aceita sem que seus conceitos sejam compreendidos pelo desenvolvedor.

O aprendizado sempre terá prioridade sobre a velocidade de desenvolvimento.

---

# Considerações Finais

Estes padrões deverão evoluir junto com a plataforma.

Sempre que uma nova tecnologia for incorporada, este documento deverá ser revisado para refletir as novas convenções adotadas.

O objetivo é manter a Akeen Commerce Data Platform organizada, consistente e próxima dos padrões encontrados em equipes profissionais de Engenharia de Dados.