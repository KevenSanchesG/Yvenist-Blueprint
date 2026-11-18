# AGENT AND SKILL CATALOG
**Release do Blueprint:** `1.0.0`

**Versão:** 0.5  
**Status:** `PROPOSAL`  
**Princípio:** a lista define responsabilidades candidatas; só criar agentes/Skills quando houver tarefa recorrente, escopo claro, ferramentas necessárias e benefício maior que o custo de coordenação.

## 1. Diferença de finalidade

- **CLAUDE.md:** contexto e instruções gerais de projeto; não deve virar manual enciclopédico.
- **Rules:** instruções persistentes e específicas de domínio/caminho.
- **Skills:** procedimentos reutilizáveis carregados quando relevantes ou invocados. Cada pasta de Skill contém `SKILL.md`.
- **Subagents:** especialistas delegados para investigar, analisar ou executar um escopo delimitado, com contexto e ferramentas próprias.
- **Hooks:** automações determinísticas acionadas por eventos; não são agentes e não substituem revisão de segurança.
- **MCP:** conexão a ferramentas/dados externos; não é uma Skill nem uma autorização automática para acessar tudo.

## 2. Papéis de sessão — não confundir com subagentes

A colaboração entre duas sessões Claude Code independentes é diferente da delegação de subagentes dentro de uma única sessão.

- `Session A — Coordinator`: função operacional atribuída a uma sessão principal; mantém registro central, divide tarefas e integra entregas.
- `Session B — Specialist/Worker`: função operacional atribuída à outra sessão; executa um workstream delimitado e entrega handoff.

Esses papéis não são arquivos de subagente em `.claude/agents/`, não criam uma hierarquia de autoridade humana e podem ser reatribuídos entre sessões por ciclo. Deve existir apenas um Coordinator por ciclo. Detalhes: `00_GOVERNANCE_AND_PROJECT_CONTROL/MULTI_SESSION_COLLABORATION/`.

Duas sessões independentes do Desktop Code com mensagens cross-session não são **Agent Teams**. Agent Teams é um recurso distinto de orquestração com lista compartilhada de tarefas e está disponível no CLI/Agent SDK, não na interface Desktop. Este Blueprint usa sessões independentes, mensagens cross-session, Git worktrees e handoffs, não Agent Teams.

## 3. Agentes candidatos

| Agente candidato | Missão | Entregáveis típicos | Limites |
|---|---|---|---|
| `product-strategy-lead` | Analisar visão, valor, portfólio, MVP e prioridade | opções, briefs, critérios, roadmap proposto | não aprova estratégia ou orçamento |
| `research-analyst` | Planejar pesquisa, avaliar fontes e sintetizar evidência | plano, matriz de evidências, insights, incertezas | não inventa entrevistas, dados ou resultados |
| `business-service-domain-analyst` | Modelar serviços, regras, entidades, estados e exceções | blueprint, regras, modelo de domínio, state machine | não aprova política comercial/jurídica |
| `marketplace-operations-analyst` | Mapear oferta, onboarding, liquidez, suporte e fulfillment | SOPs, indicadores, capacidade e incidentes | não declara capacidade operacional sem evidência |
| `brand-ux-design-lead` | Integrar identidade, conteúdo, UX e experiência | direção, fluxos, critérios visuais e de conteúdo | não muda decisões aprovadas sem gate |
| `design-system-specialist` | Especificar tokens, componentes e handoff | tokens, componentes, estados, QA | não inventa acesso ou componentes remotos Figma |
| `technical-architect-developer` | Auditar e desenhar arquitetura/implementação | ADRs, contratos, plano técnico, vertical slices | alterações de alto impacto exigem aprovação |
| `data-analytics-specialist` | Definir eventos, métricas, qualidade e personalização | taxonomia, KPI, dashboards e hipóteses de recomendação | não autoriza tratamento de dados ou profiling |
| `trust-risk-compliance-analyst` | Mapear controles, risco, fraude, privacidade e compliance | matriz de risco, controles, questões para especialistas | não fornece parecer jurídico nem certifica segurança |
| `qa-release-operations-reviewer` | Revisar qualidade, acessibilidade, testes e prontidão | relatórios, evidências, riscos e recomendação de gate | não aprova lançamento final |

## 4. Skills candidatas

| Skill | Gatilho/uso | Saída mínima |
|---|---|---|
| `project-discovery-audit` | Início de trabalho ou repositório desconhecido | inventário, baseline, lacunas e riscos |
| `blueprint-documentation` | Criar/atualizar documentos | documento com status, fontes, proprietário e links |
| `evidence-based-research` | Pesquisa externa ou de usuários | fontes, datas, evidência, limitações e síntese |
| `product-and-business-strategy` | Definir estratégia ou proposta de valor | opções, hipóteses, métricas e decisões pendentes |
| `define-and-prioritize-feature` | Transformar necessidade em escopo de feature | brief, prioridade, dependências e aceite |
| `service-blueprint-and-domain-model` | Especificar serviço e operações | blueprint, regras, entidades, estados, exceções |
| `map-user-journey-and-state-machine` | Jornada ou transição de estado | fluxo atual/futuro e state machine |
| `marketplace-operations-design` | Processo de fornecedor, suporte ou fulfillment | SOP, papéis, SLAs propostos e métricas |
| `brand-and-visual-exploration` | Exploração de identidade | brief, princípios, rotas visuais e critérios |
| `figma-and-design-system-workflow` | Trabalho de Figma e handoff | plano de integração, componentes e QA |
| `technical-architecture-review` | Auditoria ou decisão técnica | opções, ADR, impactos e riscos |
| `implement-vertical-slice` | Implementação autorizada | fluxo funcional, testes e documentação |
| `test-and-quality-review` | Validação de entrega | testes executados, resultados e defeitos |
| `analytics-and-metrics-design` | Instrumentação e métricas | eventos, definições, fórmulas e governança |
| `release-and-operations-readiness` | Preparação de release | checklist, rollback, suporte e monitoramento |
| `approval-gate-review` | Revisão de portão | evidências, pendências e recomendação de aprovação |

## 5. Critérios para criar cada agente/Skill

Antes de criar, responder:

1. A responsabilidade é recorrente e suficientemente distinta?
2. Pode ser realizada por instrução simples sem delegação?
3. Quais documentos de fonte de verdade deverá consultar?
4. Quais ferramentas realmente precisa?
5. Quais ferramentas/dados devem ser negados?
6. O que pode alterar e o que apenas pode recomendar?
7. Qual formato de saída será avaliado?
8. Como testar que a definição funciona?

## 6. Regras de implementação

- Começar com o menor conjunto útil; não ativar todos os agentes ao mesmo tempo.
- Preferir subagentes de pesquisa/análise independentes para tarefas paralelizáveis e de baixo risco.
- Não delegar a agentes decisões humanas nem tarefas com dependências de contexto não fornecido.
- Definir ferramentas mínimas por agente; não conceder acesso irrestrito por conveniência.
- Cada Skill deverá ter `SKILL.md`, descrição útil e instruções claras; referências auxiliares somente quando necessárias.
- Cada agente deverá usar formato/documentação vigente do Claude Code e ter escopo, ferramentas, restrições e entregáveis validados.
- Não criar Skills redundantes que apenas envolvam um prompt de uma linha.
- Manter um catálogo de testes e exemplos para avaliar as Skills/agentes após atualizações.


## 7. Duas sessões Desktop x Agent Teams

A coordenação entre `YV-COORD` e `YV-WORKER` utiliza **duas sessões independentes** do Claude Code Desktop, mensagens cross-session quando disponíveis e Git worktrees. Isso não é o recurso Agent Teams. Agent Teams possui coordenação e lista de tarefas compartilhada, mas não está disponível na interface Desktop no momento desta baseline. Não criar instruções que dependam de Agent Teams para o fluxo Desktop. A lista de agentes/subagentes de cada sessão e o canal de mensagens entre sessões têm escopos distintos.

Referências: `https://code.claude.com/docs/pt/cross-session-messaging` e `https://code.claude.com/docs/pt/desktop`.
