# Organization Audit — Work Brain Trabalhista

Data: 2026-10-02. Auditoria anterior às alterações V2. Consulta autenticada da API GitHub com a conta configurada no Git; inventário completo retornou dois repositórios. Nenhuma credencial registrada.

## Estado encontrado

| Repositório | Visibilidade | Branch | Base auditada | Papel |
|---|---|---|---|---|
| `.github` | público | main | `5533a73` | Perfil e documentação institucional |
| `work-brain-zamp` | privado | main | `cdecde0` | Único cliente piloto |

Acesso de escrita disponível em ambos. Nenhum repositório adicional de cliente, utilitário, experimento, Cross ou Index encontrado no inventário autenticado. Nomes de outros clientes no perfil eram exemplos futuros, não repositórios existentes.

## .github

Arquivos originais: `README.md` (apenas título) e `profile/README.md` (documentação extensa). Não havia RULEBOOK, padrão, brain, activity, workflows de CI ou AGENTS. O perfil referenciava RULEBOOK inexistente, propunha core futuro e usava clientes fictícios na navegação. Preservar: contexto por cliente, ruleset compartilhado, análise por pergunta, transporte separado, reprodutibilidade, simplicidade e segurança. Atualizar referências/modelo sem apagar o conteúdo útil.

## ZAMP

HEAD remoto coincide com checkout local. Trabalho da POC ainda não commitado: 12 documentos de memória e instrução da POC não rastreada; preservar integralmente. Fontes: README, duas análises, YAML, CLI/configuração/conector, fixtures sintéticos e testes. Auditoria detalhada privada: [ZAMP AUDIT](https://github.com/Work-brain-Trabalhista/work-brain-zamp/blob/workbrain/org-v2/brain/AUDIT.md).

Cinco unidades identificadas com confiança: Agreement Count e Risk Analysis (analysis); CLI e Metabase Connector (tool); Ruleset (other). Produto POC agregado, sem unidade independente adicional. Nenhum workflow independente, dashboard, prompt real, SQL, pipeline de ingestão ou automação noturna encontrado. Regras/schema são fictícios; uso real não comprovado.

## Atende / falta / não mover

- Atende: repositório por cliente, separação de interpretação/transporte/análises, testes locais e memória ZAMP preparada na POC.
- Criar: RULEBOOK, WORK_BRAIN_STANDARD, memória/índice organizacional, contrato activity e Cross vazio controlado.
- Atualizar: entrada de navegação do cliente, perfil institucional e referências do README .github.
- Não mover: código, ruleset, fixtures ou documentação de análises; os índices mapeiam caminhos reais. Nenhuma abstração extraída.

## Segurança e ambiguidades

`.github` é público, ZAMP privado. O índice público deve conter apenas metadados mínimos de descoberta já coerentes com o perfil, sem regras, resultados, dados pessoais, credenciais ou conteúdo do cliente. Links para repositórios privados não concedem acesso: verificar permissão antes de ler cada BRAIN. Cross será criado privado como padrão conservador para futuras capacidades internas; nenhuma promoção autorizada nesta execução.

README ZAMP chama a análise de acordos de Active, mas a memória usa experimental pelo caráter fictício; preservado e explicado. Outros clientes não encontrados; não criar entradas como se existissem. Daily Ingest e snapshots são PLANEJADOS. Nenhuma alteração de produção necessária.
