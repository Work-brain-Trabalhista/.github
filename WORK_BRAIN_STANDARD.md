# Work Brain Standard — V2

## Contrato do cliente

No caminho real do repositório: README como entrada; brain/README.md (manutenção), CLIENT.md (contexto), INDEX.md (mapa), CROSS_CANDIDATES.md (sugestões), activity/README.md (contrato futuro). Ruleset existente permanece fonte de regras. Não criar analyses/workflows vazios só para cumprir uma árvore ideal.

Cada unidade relevante identificada com confiança recebe BRAIN.md no próprio caminho. Tipos: analysis, workflow, product, tool, other. Status: experimental, active, stable, deprecated. O status deve ser sustentado pela evidência; explicitar uso demonstrativo e ausência de validação real. Variante equivalente dos títulos existentes na POC ZAMP é aceita, sem reescrita cosmética.

## Template mínimo

```md
# Brain — <nome>

## Identidade
Cliente:
Tipo:
Status:

## Objetivo
## Resultado esperado
## Como funciona hoje
## Entradas
## Fontes de dados
## Saídas
## Regras de negócio
## Decisões importantes
## Dependências
## Arquivos principais
## Estado atual
## O que mudou recentemente
## Limitações
## Pendências
## Possíveis candidatos a Cross
## Evidências / origem
```

Preencher com conteúdo real e conciso, sem dump de código, conversa de LLM, credenciais ou dados pessoais. Usar IMPLEMENTADO / PLANEJADO / HIPÓTESE / DISCUSSÃO. Sem evidência: não documentado atualmente. Apontar fontes junto às afirmações; datas de mudança apenas quando sustentadas. “Pergunta / resultado esperado” e “Regras de negócio relevantes” atendem às seções equivalentes.

## Índices

Client Index mapeia caminhos reais e tópicos sem repetir BRAIN inteiro. Organization Index vive neste repositório em brain/INDEX.md e registra cliente, unidade, tipo, tópicos, repositório/localização, link BRAIN, status e última atualização relevante. Diferenciar data de implementação de atualização documental. Links devem apontar à branch onde o conteúdo realmente existe; após merge autorizado, atualizar para a branch padrão.

Não listar clientes hipotéticos como existentes. Produto agregado pode ser descrito sem nova unidade contada. Cross Index lista somente conteúdo promovido; candidatos continuam no cliente. Visibilidade e acesso seguem [RULEBOOK](RULEBOOK.md).

## Manutenção e revisão

Identificar unidade afetada no diff → atualizar memória com evidência → ajustar índices se necessário → validar links/paths/segredos/estados e ausência de mudança funcional. Preservar documentação útil e justificar substituições. Activity é contrato futuro, sem reconstrução de histórico. Snapshots/ingest seguem o gate do Rulebook; não foram automatizados.
