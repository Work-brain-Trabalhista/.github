<div align="center">

# ⚖️ Work Brain · Trabalhista

### Inteligência, padronização e conhecimento aplicado ao contencioso trabalhista

Organização central de conhecimento, regras e análises trabalhistas estruturadas por cliente.

</div>

---

## 🧠 Sobre o Work Brain

O **Work Brain Trabalhista** organiza conhecimento, regras de negócio, fontes de dados e análises relacionadas ao contencioso trabalhista de forma estruturada, reproduzível e específica para cada cliente.

A arquitetura parte de um princípio simples:

> **Cada cliente possui seu próprio contexto e sua própria fonte de verdade.**

Por isso:

- **um repositório representa um cliente;**
- **um ruleset concentra o conhecimento compartilhado daquele cliente;**
- **cada análise representa uma pergunta ou problema específico;**
- **connectors definem como os dados são obtidos;**
- **prompts definem como modelos de linguagem devem trabalhar, quando aplicável.**

```mermaid
flowchart TD
    A["🏢 Cliente"]
    B["📐 Ruleset"]
    D["🔌 Fontes de dados"]

    subgraph C["📊 Análises"]
        E["Análise A"]
        F["Análise B"]
        G["Análise C"]
    end

    H["📦 Resultados"]

    A -->|"define contexto"| B
    A -->|"possui"| D
    A -->|"contém"| C

    B -->|"regras"| E
    B -->|"regras"| F
    B -->|"regras"| G

    D -->|"dados"| E
    D -->|"dados"| F
    D -->|"dados"| G

    E -->|"gera"| H
    F -->|"gera"| H
    G -->|"gera"| H

    classDef client fill:#1f4e79,color:#fff,stroke:#163a5a,stroke-width:1px;
    classDef ruleset fill:#6a1b9a,color:#fff,stroke:#4a136d,stroke-width:1px;
    classDef datasource fill:#ef6c00,color:#fff,stroke:#b45309,stroke-width:1px;
    classDef analysis fill:#1565c0,color:#fff,stroke:#0d47a1,stroke-width:1px;
    classDef result fill:#2e7d32,color:#fff,stroke:#1b5e20,stroke-width:1px;

    class A client;
    class B ruleset;
    class D datasource;
    class E,F,G analysis;
    class H result;
```


---

## 📚 Documentação

A documentação do Work Brain é dividida em dois níveis:

- **[RULEBOOK.md](https://github.com/work-brain-trabalhista/.github/blob/main/RULEBOOK.md)** — arquitetura, convenções e regras para criar clientes, analyses, rulesets, connectors e prompts.
- **README de cada cliente** — contexto específico, análises disponíveis, fontes de dados e instruções de execução daquele cliente.

> O README desta organização funciona como mapa.  
> O Rulebook define como o sistema deve ser construído.

---

## 🗂️ Clientes

Cada cliente possui um repositório próprio e independente.

| Cliente | Repositório | Análises | Status |
|---|---|---:|---|
| **Zamp** | [`work-brain-zamp`](https://github.com/work-brain-trabalhista/work-brain-zamp) | 1+ | 🟢 Ativo |
| **Cliente B** | `work-brain-cliente-b` | — | ⚪ Futuro |
| **Cliente C** | `work-brain-cliente-c` | — | ⚪ Futuro |

> O README de cada cliente funciona como índice para todas as análises disponíveis naquele contexto.

---

## 🧩 Arquitetura

A organização segue a estrutura:

```text
GitHub Organization · work-brain-trabalhista
│
├── .github
│   ├── RULEBOOK.md
│   │
│   └── profile/
│       └── README.md
│
├── work-brain-zamp
│   ├── README.md
│   ├── ruleset/
│   ├── analyses/
│   ├── prompts/
│   ├── docs/
│   └── tests/
│
├── work-brain-cliente-b
│   ├── README.md
│   ├── ruleset/
│   ├── analyses/
│   ├── prompts/
│   ├── docs/
│   └── tests/
│
└── work-brain-core
    └── futuro, caso componentes realmente compartilhados
        entre clientes sejam identificados
```

### Modelo mental

```text
ORGANIZAÇÃO
     │
     └── CLIENTE
            │
            ├── RULESET
            │      conhecimento compartilhado
            │
            ├── CONNECTORS
            │      acesso aos dados
            │
            ├── ANALYSES
            │      ├── pergunta A
            │      ├── pergunta B
            │      └── pergunta C
            │
            ├── PROMPTS
            │      instruções para LLMs
            │
            └── DOCS
                   contexto complementar
```

---

## 📐 Rulesets

Cada cliente possui um **ruleset próprio**, que funciona como a fonte estruturada de conhecimento compartilhado entre suas análises.

O ruleset concentra definições e regras que devem permanecer consistentes independentemente da análise executada.

| Categoria | Exemplos |
|---|---|
| **Identificação** | aliases, IDs e nomenclaturas do cliente |
| **Dados** | mappings de campos, normalizações e classificações |
| **Regras de negócio** | definição de acordo, critérios específicos, políticas |
| **Thresholds** | limites financeiros, faixas e critérios de decisão |
| **Classificações** | categorias, tags, prioridades e status |
| **Exceções** | situações que modificam ou sobrescrevem regras padrão |

Exemplo:

```text
Ruleset Zamp
     │
     ├── Agreement Count
     ├── Average Agreement Value
     ├── Provision Analysis
     └── Risk Analysis
```

A regra prática é:

> **Se uma definição precisa permanecer igual entre várias análises do mesmo cliente, ela provavelmente pertence ao ruleset.**

### Ruleset não é Analysis

```text
"Status homologado é considerado acordo."
                    │
                    ▼
                 RULESET
```

```text
"Quantos acordos ocorreram?"
                    │
                    ▼
                 ANALYSIS
```

Também não deve ser confundido com prompt ou connector:

```text
Ruleset
→ conhecimento e regras

Analysis
→ pergunta que queremos responder

Connector
→ como os dados são obtidos

Prompt
→ como uma LLM deve trabalhar
```

---

## 📊 Analyses

Uma **analysis** representa uma pergunta, problema ou resultado específico que queremos produzir dentro do contexto de um cliente.

Exemplos:

```text
Quantos acordos ocorreram?

Qual o valor médio dos acordos?

Qual a taxa de acordo?

Qual o volume de processos?

Qual a exposição financeira?

Quais processos apresentam maior risco?
```

Cada análise deve existir dentro de:

```text
analyses/
```

Exemplo:

```text
work-brain-zamp/
│
└── analyses/
    ├── agreement_count/
    │   ├── README.md
    │   └── analysis.py
    │
    ├── average_agreement_value/
    │   ├── README.md
    │   └── analysis.py
    │
    └── risk_analysis/
        ├── README.md
        └── analysis.py
```

Cada análise reutiliza, sempre que aplicável, o mesmo ruleset e a mesma infraestrutura do cliente.

---

## 🔌 Connectors

Connectors são responsáveis exclusivamente por acessar fontes de dados.

Exemplos:

```text
Metabase
PostgreSQL
API interna
CSV
Google Sheets
```

O fluxo esperado é:

```mermaid
flowchart LR
    A["Fonte de dados"] --> B["Connector"]
    B --> C["Dados"]
    C --> D["Ruleset"]
    D --> E["Analysis"]
    E --> F["Resultado"]
```

Um connector deve saber:

> **Como buscar os dados?**

Ele não deve decidir:

> **O que é um acordo?**  
> **Qual processo é de alto risco?**  
> **Qual regra específica do cliente deve ser aplicada?**

Essas responsabilidades pertencem ao ruleset e à análise.

---

## 🏗️ Estrutura padrão de um cliente

Um repositório deve seguir aproximadamente:

```text
work-brain-<client>/
│
├── README.md
├── pyproject.toml
├── .env.example
├── .gitignore
│
├── ruleset/
│   ├── README.md
│   └── <client>.yaml
│
├── analyses/
│   ├── README.md
│   │
│   ├── analysis_a/
│   │   ├── README.md
│   │   └── analysis.py
│   │
│   └── analysis_b/
│       ├── README.md
│       └── analysis.py
│
├── src/
│   └── work_brain/
│       ├── config.py
│       ├── ruleset.py
│       └── connectors/
│
├── prompts/
│
├── docs/
│
├── fixtures/
│
└── tests/
```

O `README.md` do cliente deve ser o **ponto inicial para qualquer pessoa ou agente que precise trabalhar naquele contexto**.

---

## 🧭 Onde cada coisa deve ficar?

| Pergunta | Lugar |
|---|---|
| Mudou porque mudou o cliente? | `ruleset/` |
| Mudou porque mudou a pergunta? | `analyses/` |
| Mudou porque mudou a fonte de dados? | `connectors/` |
| É instrução para uma LLM? | `prompts/` |
| É documentação complementar? | `docs/` |
| É código realmente compartilhado? | `src/` |
| É validação de comportamento? | `tests/` |

Em forma resumida:

```text
Mudou o cliente?
→ RULESET

Mudou a pergunta?
→ ANALYSIS

Mudou a fonte?
→ CONNECTOR

Mudou a instrução para IA?
→ PROMPT

É explicação?
→ DOCS
```

---

## 📋 Contrato mínimo de um repositório

Cada cliente deve documentar:

| Área | O que deve estar definido |
|---|---|
| **Contexto** | quem é o cliente e qual o contexto da operação |
| **Ruleset** | conhecimento e regras compartilhadas |
| **Dados** | fontes, schemas e mappings utilizados |
| **Análises** | perguntas e soluções disponíveis |
| **Prompts** | instruções para LLMs, quando aplicável |
| **Saídas** | estrutura e significado dos resultados |
| **Validação** | como verificar regras e análises |
| **Limitações** | situações não contempladas ou que exigem revisão humana |

---

## 🚀 Criando uma nova análise

Uma análise nova deve nascer **dentro do repositório do cliente**.

```text
Cliente
   ↓
Problema / pergunta
   ↓
Dados
   ↓
Ruleset
   ↓
Analysis
   ↓
Validação
   ↓
Resultado
```

Por exemplo:

```text
work-brain-zamp/
│
└── analyses/
    └── agreement_count/
```

e não:

```text
zamp-agreement-count/
```

como um novo repositório.

Para instruções completas sobre criação de análises e novos clientes, consulte o **[Work Brain Rulebook](https://github.com/work-brain-trabalhista/.github/blob/main/RULEBOOK.md)**.

---

## 🧭 Princípios

> **Context before analysis.**  
> Primeiro entenda o cliente e o contexto. Depois aplique regras e execute a análise.

> **Explicit rules over implicit knowledge.**  
> Conhecimento importante não deve existir apenas na cabeça de quem escreveu o código.

> **One client, one source of truth.**  
> As regras compartilhadas de um cliente devem possuir uma fonte de verdade clara.

> **Analyses should be reproducible.**  
> Deve ser possível compreender quais dados, regras e versões produziram determinado resultado.

> **Documentation is part of the product.**  
> Uma análise que apenas seu autor entende ainda não está pronta.

> **Prefer simple structures.**  
> Não transformar o Work Brain em um framework antes que exista necessidade real.

---

## 🔐 Segurança e confidencialidade

Os repositórios podem conter conhecimento interno relacionado às operações de contencioso trabalhista.

Nunca devem ser versionados:

- credenciais;
- API keys;
- tokens;
- senhas;
- arquivos `.env`;
- dados pessoais desnecessários;
- documentos processuais completos sem necessidade;
- informações confidenciais fora do escopo da análise.

Exemplos e testes devem utilizar, sempre que possível, **dados fictícios ou anonimizados**.

---

## 🔮 Componentes compartilhados

Neste estágio, cada repositório de cliente deve ser preferencialmente autocontido.

Não devemos criar abstrações compartilhadas prematuramente.

Quando componentes forem claramente reutilizados entre diversos clientes, poderá surgir:

```text
work-brain-core
```

com componentes como:

```text
MetabaseConnector
RulesetLoader
Configuration
Logging
Result Models
CLI Utilities
```

O `work-brain-core` nunca deverá conter regras específicas de clientes.

---

## 🗺️ Navegação

```mermaid
flowchart TD
    HOME["⚖️ Work Brain Trabalhista"]

    HOME --> RULEBOOK["📖 Rulebook"]

    HOME --> ZAMP["🏢 Zamp"]
    HOME --> B["🏢 Cliente B"]
    HOME --> C["🏢 Cliente C"]

    ZAMP --> ZR["📐 Ruleset"]
    ZAMP --> ZA["📊 Analyses"]
    ZAMP --> ZD["📚 Docs"]

    ZA --> ZA1["Agreement Count"]
    ZA --> ZA2["Future Analysis"]
    ZA --> ZA3["Future Analysis"]
```

---

<div align="center">

### ⚖️ Work Brain · Trabalhista

**Contexto → conhecimento estruturado → regras explícitas → análises reproduzíveis**

</div>
