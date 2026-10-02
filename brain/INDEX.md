# Work Brain — Organization Index

Atualizado: 2026-10-02. Catálogo de metadados para descoberta, não cópia de contexto de cliente. Links ZAMP apontam para main após a integração da POC; Cross mantém sua branch padrão workbrain/org-v2. Acesso privado continua sujeito a permissões.

## ZAMP

Repositório privado [work-brain-zamp](https://github.com/Work-brain-Trabalhista/work-brain-zamp). [Client Brain](https://github.com/Work-brain-Trabalhista/work-brain-zamp/blob/main/brain/CLIENT.md) · [Client Index](https://github.com/Work-brain-Trabalhista/work-brain-zamp/blob/main/brain/INDEX.md).

| Cliente | Unidade | Tipo | Tópicos | Localização | Brain | Status | Última atualização relevante |
|---|---|---|---|---|---|---|---|
| ZAMP | Agreement Count | analysis | acordos, contagem, deduplicação | `work-brain-zamp/analyses/agreement_count/` | [BRAIN](https://github.com/Work-brain-Trabalhista/work-brain-zamp/blob/main/analyses/agreement_count/BRAIN.md) | experimental | 2026-10-02 (memória) |
| ZAMP | Risk Analysis | analysis | risco demonstrativo, categorias | `work-brain-zamp/analyses/risk_analysis/` | [BRAIN](https://github.com/Work-brain-Trabalhista/work-brain-zamp/blob/main/analyses/risk_analysis/BRAIN.md) | experimental | 2026-10-02 (memória) |
| ZAMP | CLI | tool | execução, offline, configuração | `work-brain-zamp/src/work_brain/` | [BRAIN](https://github.com/Work-brain-Trabalhista/work-brain-zamp/blob/main/src/work_brain/BRAIN.md) | experimental | 2026-10-02 (memória) |
| ZAMP | Metabase Connector | tool | fonte de dados, transporte HTTP | `work-brain-zamp/src/work_brain/connectors/` | [BRAIN](https://github.com/Work-brain-Trabalhista/work-brain-zamp/blob/main/src/work_brain/connectors/BRAIN.md) | experimental | 2026-10-02 (memória) |
| ZAMP | Ruleset ZAMP | other | interpretação, regras compartilhadas | `work-brain-zamp/ruleset/` | [BRAIN](https://github.com/Work-brain-Trabalhista/work-brain-zamp/blob/main/ruleset/BRAIN.md) | experimental | 2026-10-02 (memória) |

Produto agregado: POC de análises via CLI; sem unidade independente adicional. Nenhum workflow independente encontrado. Implementação de exemplo anterior à memória; dados/regras não validados para operação real. Não há outros clientes no inventário autenticado desta execução.

## Cross

Destino controlado: [work-brain-cross](https://github.com/Work-brain-Trabalhista/work-brain-cross), privado; [Index](https://github.com/Work-brain-Trabalhista/work-brain-cross/blob/workbrain/org-v2/brain/INDEX.md). Nenhuma unidade promovida: 0. Sugestões permanecem no [cliente de origem](https://github.com/Work-brain-Trabalhista/work-brain-zamp/blob/main/brain/CROSS_CANDIDATES.md).

## Tópicos

- Acordos/contagem: Agreement Count e Ruleset.
- Risco/categorias: Risk Analysis e Ruleset.
- Fontes/execução: CLI e Metabase Connector.
- Memória/proveniência: [STANDARD](../WORK_BRAIN_STANDARD.md), [RULEBOOK](../RULEBOOK.md).

## Descoberta

Pergunta do agente → este Index → unidade/repositório → verifica permissão → carrega somente BRAIN relevante. Cross não dá acesso ao contexto de outros clientes. Relações entre clientes ainda não identificadas; **PLANEJADO:** ingest futuro sugerirá relações com evidências.
