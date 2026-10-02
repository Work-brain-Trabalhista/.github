# Work Brain Rulebook

Padrão V2 — 2026-10-02. Client contém contexto; Index conecta contexto; Cross contém conhecimento reutilizável.

## Princípios preservados

Contexto antes da análise; regras explícitas; uma fonte de verdade por cliente; análises reproduzíveis; documentação como parte do produto; estruturas simples. Reutilizar rulesets e connectors, sem repetir regras do cliente em cada pergunta. Exemplos e testes devem usar dados fictícios ou anonimizados. Origem: [perfil institucional](profile/README.md), existente antes desta revisão.

## Responsabilidades

| Conceito | Responsabilidade |
|---|---|
| Client | Repositório e contexto específico de um cliente |
| Ruleset | Interpretação, mappings e regras compartilhadas do cliente |
| Analysis | Pergunta, cálculo ou análise com resultado específico |
| Workflow | Processo de múltiplas etapas ou transformação operacional |
| Product | Produto maior que agrupa analyses/workflows, somente quando houver evidência |
| Connector | Acesso e transporte de dados, sem definir regras do cliente |
| Prompt | Instrução versionada de LLM quando necessária, com unidade consumidora |
| BRAIN.md | Memória semântica de unidade real, com estado, decisões e evidências |
| Client Brain | Contexto consolidado e mapa local em brain/ |
| Brain Index | Localiza unidades e relaciona metadados, sem concentrar contextos completos |
| Cross | Somente capacidades ou conhecimento aprovados como independentes do cliente |
| Daily Ingest | Consolidação futura de mudanças da memória |

Analysis responde principalmente uma pergunta (taxa de acordos, exposição financeira); workflow transforma ou coordena etapas (classificação documental, tombamento). Esses exemplos não afirmam que tais unidades existem nesta organização. Uma CLI síncrona não implica workflow independente, e um diretório não implica produto.

## Organização e caminhos

Um repositório por cliente. O control plane conceitual vive em `.github`, com [padrão](WORK_BRAIN_STANDARD.md), [índice](brain/INDEX.md) e [auditoria](brain/ORG_AUDIT.md). Não criar repositório work-brain-index nesta versão.

Preservar paths reais: primeiro fazer o Brain entender o código existente. BRAIN.md fica junto à unidade mesmo fora de analyses/workflows. Não mover aplicações em massa ou criar diretórios artificiais. Cada README de cliente aponta para seu Client Brain e Index. Rulesets continuam fonte oficial de regras; CLIENT.md referencia, não replica.

## Memória e proveniência

Usar [WORK_BRAIN_STANDARD.md](WORK_BRAIN_STANDARD.md). Não inventar; usar “não encontrado” ou “não documentado atualmente”. Distinguir **IMPLEMENTADO**, **PLANEJADO** e **HIPÓTESE / DISCUSSÃO**. Status não significa validação em produção. Regras, decisões, fontes, resultados e mudanças relevantes apontam para arquivos/testes/commits. Não reconstruir histórico antigo artificialmente ou duplicar README como memória.

## Descoberta entre clientes

Agente do cliente → consulta Organization Index → encontra cliente/unidade ou Cross → verifica acesso/permissão → carrega somente o BRAIN relevante. Cross não é ponte para ler contexto de outros clientes. O índice não concede permissões e não torna públicos os dados de origem.

Este `.github` é público. Publicar apenas metadados de descoberta adequados à visibilidade: nunca regras internas, resultados reais, dados pessoais ou material confidencial de cliente. Conhecimento restrito permanece no repositório com controle de acesso. Reavaliar visibilidade antes de ampliar metadados; esta mudança não altera permissões dos repositórios existentes.

## Promoção para Cross

1. Registrar candidato no CROSS_CANDIDATES.md do cliente, com origem, parte genérica e dependências específicas.
2. Avaliar reutilização concreta, contrato, testes, segurança, proveniência e acesso.
3. Obter validação humana explícita da promoção.
4. Só então publicar capacidade independente em Cross e atualizar índices/origens.

Candidato não é aprovação. Não copiar contexto, YAML específico, fixtures ou documentos de cliente para Cross. Cross pode começar vazio. Não criar abstrações genéricas prematuras.

## Agente pessoal, ingest e preservação

**PLANEJADO:** pessoa trabalha → agente autorizado (Codex, ChatGPT/Desktop ou outro) identifica unidade afetada → atualiza BRAIN e decisões → prepara snapshot → gate → commit/push de preservação → Daily Ingest lê BRAIN alterados → atualiza Client Brain/Org Index → detecta relações → sugere candidatos.

Agente pessoal atua somente no projeto autorizado; não vasculha a máquina, não promove Cross sozinho, não altera regras institucionais silenciosamente e não faz force push. Ingest deve preferir memória alterada a reinterpretar toda a base diariamente. Nenhum scheduler, ingest ou snapshot automático foi implementado nesta revisão.

Antes de automação Git futura: **allowlist + denylist + secret scan + revisão de git diff**. Registrar status e seleção; nunca `git add -A` sem filtros. Excluir `.env`/variantes, tokens, API keys, chaves privadas, certificados/credenciais, dumps, arquivos pessoais, documentos processuais desnecessários, dados confidenciais fora do escopo, paths não autorizados e artefatos grandes sem política. Exemplo fictício de mensagem: `[brain] daily snapshot YYYY-MM-DD`.

## Mudanças e validação

Inspecionar status/branch/log antes de editar. Preservar trabalho local. Usar branch dedicada e commits lógicos, sem merge automático em main, rebase destrutivo, force push ou exclusão de branches. Não alterar produção, Cards, SQL ou infraestrutura para adequar documentação; não fazer deploy.

Validar links/paths, evidências, distinção de estados, segredos, diff e ausência de alteração funcional. Registrar limites e lacunas. Contrato de atividade: [brain/activity/README.md](brain/activity/README.md).
