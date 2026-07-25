# MEMORY.md

> Memória viva do projeto **Akeen Coffee Commerce Data Platform (ACDP)**.
>
> Este documento registra apenas informações permanentes e contexto relevante para continuidade do projeto entre diferentes sessões. Não substitui a documentação técnica nem o changelog.

---

# Objetivo do Projeto

Construir uma plataforma moderna de Engenharia de Dados, simulando um ambiente corporativo real e aplicando boas práticas de arquitetura, DataOps, Analytics Engineering e governança de dados.

O objetivo principal é desenvolver conhecimento profundo das tecnologias utilizadas por Engenheiros de Dados Pleno/Sênior, produzindo um portfólio profissional de alta qualidade.

---

# Filosofia do Projeto

* Aprender os conceitos antes da implementação.
* Priorizar qualidade de engenharia em vez de velocidade.
* Simular decisões tomadas em empresas reais.
* Justificar tecnicamente todas as decisões arquiteturais.
* Evoluir o projeto incrementalmente utilizando a abordagem Walking Skeleton.
* Documentar decisões importantes através de ADRs (Architecture Decision Records).

---

# Domínio de Negócio

Empresa fictícia:

**Akeen Coffee Commerce**

Segmento:

E-commerce especializado na comercialização de cafés especiais, grãos, acessórios e produtos relacionados ao universo do café.

O domínio foi escolhido por afinidade com o tema, permitindo maior profundidade na compreensão do negócio, modelagem dimensional e definição de indicadores.

---

# Arquitetura

Arquitetura adotada:

**Lakehouse**

Camadas de dados:

* Bronze
* Silver
* Gold

Modelo analítico final:

**Star Schema**

---

# Stack Principal

* AWS
* Amazon S3
* Databricks
* Apache Spark
* Delta Lake
* Python
* Spark SQL
* dbt Core
* Git
* GitHub
* Power BI

Tecnologias poderão ser adicionadas futuramente conforme a evolução do projeto.

---

# Fonte Principal de Dados

Dataset principal:

**Coffee Bean Sales Raw Dataset (Kaggle)**

Critérios para escolha:

* Dados em estado bruto.
* Múltiplas entidades relacionadas.
* Possibilita exercitar ingestão, limpeza, modelagem e Analytics Engineering.
* Domínio alinhado ao negócio fictício.

Novas fontes poderão ser incorporadas futuramente para expandir os domínios de negócio.

---

# Metodologia de Desenvolvimento

Abordagem adotada:

**Walking Skeleton**

Estratégia:

Implementar primeiro um fluxo completo ponta a ponta (ingestão → transformação → consumo) antes de expandir funcionalidades ou aumentar a complexidade da infraestrutura.

---

# Convenções Permanentes

## Versionamento

* GitHub Flow.
* Conventional Commits.
* Pull Requests para funcionalidades relevantes.

## Dados

* Nunca versionar datasets.
* Nunca versionar arquivos gerados por ferramentas.
* Nunca versionar credenciais.

## Documentação

* `README.md` → visão geral do projeto.
* `MEMORY.md` → memória permanente do projeto.
* `PROJECT_CONTEXT.md` → contexto estável utilizado pelos assistentes.
* `CHANGELOG.md` → histórico de evolução.
* `docs/ADR/` → decisões arquiteturais.

---

# Regras para Assistentes de IA

Ao auxiliar neste projeto:

* Ler este documento antes de qualquer recomendação.
* Preservar as decisões arquiteturais já tomadas.
* Não alterar a arquitetura sem justificativa técnica.
* Explicar primeiro o conceito.
* Depois explicar a arquitetura.
* Depois propor a implementação.
* Somente então gerar código.
* Sempre conectar novos conceitos ao Data Warehouse tradicional quando possível.
* Priorizar simplicidade antes de adicionar novas ferramentas ou componentes.

---

# Estado Atual do Projeto

## Concluído

* Definição do objetivo do projeto.
* Definição da arquitetura Lakehouse.
* Definição da stack tecnológica.
* Definição da metodologia Walking Skeleton.
* Escolha do domínio de negócio (Coffee Commerce).
* Escolha do dataset principal.
* Estrutura inicial do repositório criada.
* README refatorado.

## Em andamento

* Organização da estrutura do projeto.
* Preparação da documentação base.

## Próxima etapa

* Inspecionar o schema do dataset Coffee Bean Sales Raw.
* Mapear entidades e relacionamentos.
* Planejar a ingestão para a camada Bronze.

---

# Princípio Norteador

Mais importante do que construir uma plataforma funcionando é compreender profundamente as decisões arquiteturais, os conceitos de Engenharia de Dados e as boas práticas utilizadas em ambientes corporativos modernos.

Toda evolução do projeto deve priorizar qualidade, clareza, organização e aprendizado consistente.

---

**Última atualização:** Julho de 2026.
